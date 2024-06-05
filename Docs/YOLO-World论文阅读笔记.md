
# Table of Contents

+ [YOLO-World: Real-Time Open-Vocabulary Object Detection](#org0f7d60e)
    1.  [Problem](#org5ff3ddb)
    2.  [Motivation](#org35ba814)
    3.  [Method](#org0dec54d)
        1.  [Prompt-then-detect paradigm](#orga2297d6)
        2.  [Pre-training Formulation: Region-Text Pairs](#org2c2e633)
        3.  [Architecture](#orga37817d)
        4.  [Loss](#orgd6d582b)
    4.  [Result](#org78433b0)
        1.  [zero-shot capability](#orgf4b6832)
    5.  [Contribution](#orgcbe359d)



<a id="org0f7d60e"></a>

# YOLO-World: Real-Time Open-Vocabulary Object Detection

<a id="org5ff3ddb"></a>

## Problem
1.  现有目标检测方法多为在封闭词汇集(fixed-vocabulary)上进行，即在给定类别的的训练集上进行训练，得到的模型只能对特定类别的目标进行检测。（如在 coco 数据集上训练的闭集目标检测算法就只能检测对应 80 个类别的物体）
2.  如 GroundDINO 这样的开放词汇集(open-vocabulary)目标检测方法使用较大的分割头与骨干网络，导致计算量大推理延迟高。

<a id="org35ba814"></a>

## Motivation
现有开集目标检测方法计算量大推理延迟高，但现实使用场景中对目标检测算法的实时性要求较高，因此本文基于实时目标检测算法 yolov8 设计了高效实时的开放词汇集目标检测方法 YOLO-World。

<a id="org0dec54d"></a>

## Method

<a id="orga2297d6"></a>

### Prompt-then-detect paradigm

![img](https://github.com/PaddlePaddle/PaddleMIX/assets/93063038/940e86e8-47fd-4b10-be61-228e84518457.png)

现存的开集检测方法往往维护一个在线词汇表，在每次推理的过程中都需要对输入文本进行编码来构建在线词汇表，这会增大网络对推理资源的需求，增大 latency。YOLO-World 提出了一种 Prompt-then-detect 范式，可以将给定文本编码成离线词汇表，从而避免在推理阶段反复对文本进行编码。除此之外，在 YOLO-World 中，可以使用重参数化方法，将离线词汇表(即通过 text encoder 编码得到的文本特征)参数化为 neck 中的模型参数，实现高效地部署与加速。

<a id="org2c2e633"></a>

### Pre-training Formulation: Region-Text Pairs

和传统目标检测方法不同(以 boundingbox 和 class 为标签)，YOLO-World 使用 region-text pairs 作为标签，就是以物体的 boundingbox 和对应文本对作为标签啦。

该如何大批量自动生成这样的数据集捏？本文给出了一种方案：

1.  通过 n-gram 算法提取文本中的名词短语
2.  将图片和提取的名词短语输入到 GLIP 中生成 bounding box
3.  使用 CLIP 来评估 image-text pairs 与 region-text pairs 之间的相关性，将相关性较低的筛去（附录部分提到作者设置的筛选规则是 $s=\sqrt{s^{img}*s^{region}}\leq0.3$ ）。最后再通过 nms 筛去冗余的 boundingbox。

<a id="orga37817d"></a>

### Architecture

![img](https://github.com/PaddlePaddle/PaddleMIX/assets/93063038/01f8a048-753a-4b0c-b73b-97fc01eef94e.png)

1.  Backbone: MultiModal Backbone

    backbone 分为 ImageBackbone 和 TextBackbone 两部分，分别用于图像和文本特征的提取，其中 ImageBackbone 使用与 yolov8 相同的 cspdarknet，使用 clip 作为 textbackbone。
    
2.  Neck: RepVL-PAN

    既然是多模态的方法自然少不了跨模态特征之间的交互与对齐，YOLO-World 的 neck 部分为 Re-parameterizable Vision-Language PAN，使用 Text-guided CSPLayer 替换 yolov8 中的 c2f layer 完成实现文本特征对图像特征的增强，加入 Image-Pooling Attention 实现图像特征对文本特征的增强。通过这两个模块实现了多模态特征的交互与对齐。
    
    ![img](https://private-user-images.githubusercontent.com/93063038/336705256-0537a6e7-3c67-4a55-9523-c70ce1a8c396.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTc1Njc0NTksIm5iZiI6MTcxNzU2NzE1OSwicGF0aCI6Ii85MzA2MzAzOC8zMzY3MDUyNTYtMDUzN2E2ZTctM2M2Ny00YTU1LTk1MjMtYzcwY2UxYThjMzk2LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MDUlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjA1VDA1NTkxOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTYxMDIwODQ4MDQxNzU4ZDgyMTllZTIzZGZlMDhjN2JhOGZhMTY4YTY1NWE1MjQ5YmQ5YmU4NjM2N2ZjNzQ1NGYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.8HbCO12izYpe_z9zX93m0RhMWD5SqkZ51GNYEJJ41GI)
    
    1.  T-CSPLayer
    
        ![img](https://private-user-images.githubusercontent.com/93063038/336705883-de324340-a7f7-45f1-9f19-08e4122506f0.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTc1Njc2MjUsIm5iZiI6MTcxNzU2NzMyNSwicGF0aCI6Ii85MzA2MzAzOC8zMzY3MDU4ODMtZGUzMjQzNDAtYTdmNy00NWYxLTlmMTktMDhlNDEyMjUwNmYwLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MDUlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjA1VDA2MDIwNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWMxZDMwNmViYjE0MzIxM2VjMmRiNGNiOThjZjdiNGY1NzZiNDk0NmI4MWIzZmNlZTY1MmI1MWRhMjE3MzhmZDcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.kny7Pw14WMIWQekvJqog1ySlfOeObRnqDzr6tLjHf10)
        
        上图为 c2f layer，可以发现 T-CSPLayer 事实上只是在 c2f layer 的基础上在 bottleneck layer 之后添加了一个 Max-Sigmoid Attention，其使用 paddle 实现的代码如下:

        ```python
        class MaxSigmoidAttnBlock(nn.Layer):
            """Max Sigmoid attention block."""
        
            def __init__(
                self,
                in_channels,
                out_channels,
                guide_channels,
                embed_channels,
                kernel_size=3,
                padding=1,
                num_heads=1,
                depthwise=False,
                with_scale=False,
                act="silu",
            ):
                super().__init__()
        
                assert (
                    out_channels % num_heads == 0 and embed_channels % num_heads == 0
                ), "out_channels and embed_channels should be divisible by num_heads."
                self.num_heads = num_heads
                self.head_channels = out_channels // num_heads
                Conv = DWConv if depthwise else BaseConv
        
                self.embed_conv = (
                    nn.Sequential(
                        nn.Conv2D(
                            in_channels=in_channels,
                            out_channels=embed_channels,
                            kernel_size=kernel_size,
                            padding=padding,
                        ),
                        nn.BatchNorm2D(
                            num_features=embed_channels, momentum=0.03, epsilon=0.001
                        ),
                    )
                    if embed_channels != in_channels
                    else None
                )
        
                self.guide_fc = nn.Linear(guide_channels, embed_channels)
        
                self.bias = self.create_parameter(
                    shape=[num_heads],
                    default_initializer=nn.initializer.Constant(value=0.0),
                    is_bias=True,
                )
        
                if with_scale:
                    self.scale = self.create_parameter(
                        shape=[1, num_heads, 1, 1],
                        default_initializer=nn.initializer.Constant(value=1.0),
                    )
                else:
                    self.scale = 1.0
        
                self.project_conv = Conv(
                    in_channels=in_channels,
                    out_channels=out_channels,
                    ksize=kernel_size,
                    stride=1,
                    with_act=False,
                )
        
            def forward(self, x, guide):
                B, _, H, W = x.shape
        
                guide = self.guide_fc(guide)
                guide = guide.reshape([B, -1, self.num_heads, self.head_channels])
                embed = self.embed_conv(x) if self.embed_conv is not None else x
                embed = embed.reshape([B, self.num_heads, self.head_channels, H, W])
        
                batch, num_heads, head_channels, height, width = embed.shape
                _, num_embeddings, _, _ = guide.shape
                embed = paddle.transpose(embed, perm=[0, 1, 3, 4, 2])
                embed = embed.reshape([B, num_heads, -1, head_channels])
                guide = paddle.transpose(guide, perm=[0, 2, 3, 1])
                attn_weight = paddle.matmul(embed, guide)
                attn_weight = attn_weight.reshape(
                    [batch, num_heads, height, width, num_embeddings]
                )
        
                attn_weight = attn_weight.max(axis=-1)[0]
                attn_weight = attn_weight / (self.head_channels**0.5)
                attn_weight = attn_weight + self.bias[None, :, None, None]
                attn_weight = attn_weight.sigmoid() * self.scale
        
                x = self.project_conv(x)
                x = x.reshape([B, self.num_heads, -1, H, W])
                x = x * attn_weight.unsqueeze(2)
                x = x.reshape([B, -1, H, W])
                return x
        ```
        
        为了解释为什么使用 Max-Sigmoid Attention，并且为什么要取最大值，让我们回顾一下背景。首先 TextBackbone clip 会将输入的 n 个文本编码成 n 个对应的向量。然后，通过计算文本嵌入与图像嵌入的内积得到它们的相似度作为注意力权重。我们的目标是找到与这 n 个文本编码中任意一个最相似的特征图区域，并将其赋予较高的权重。因此只需要在文本嵌入数量这一维度上取最大值，就能够实现这样的效果（如代码所示）。
    
    2.  I-Pooling Attention
  
        将三个不同尺度的图片特征使用池化(使用 nn.AdaptiveMaxPool2D 实现)下采样到 $3\times3$ 的大小后 flatten 并 concat。与文本嵌入作 multihead-attention，如下式：

        $$W' = W + MultiHead-Attention(W, X', X')$$

        其中 W 为文本嵌入，X&rsquo;为图片特征。使用 paddle 实现代码如下：

        ```python
        class ImagePoolingAttentionModule(nn.Layer):
            def __init__(
                self,
                image_channels,
                text_channels,
                embed_channels,
                with_scale=False,
                num_feats=3,
                num_heads=8,
                pool_size=3,
            ):
                super().__init__()
        
                self.text_channels = text_channels
                self.embed_channels = embed_channels
                self.num_heads = num_heads
                self.num_feats = num_feats
                self.head_channels = embed_channels // num_heads
                self.pool_size = pool_size
                if with_scale:
                    self.scale = self.create_parameter(
                        shape=[1], default_initializer=paddle.nn.initializer.Constant(0.0)
                    )
                else:
                    self.scale = 1.0
        
                self.projections = nn.LayerList(
                    [
                        BaseConv(
                            in_channels=in_channels,
                            out_channels=embed_channels,
                            ksize=1,
                            stride=1,
                            with_act=False,
                        )
                        for in_channels in image_channels
                    ]
                )
                self.query = nn.Sequential(
                    nn.LayerNorm(text_channels), nn.Linear(text_channels, embed_channels)
                )
                self.key = nn.Sequential(
                    nn.LayerNorm(embed_channels), nn.Linear(embed_channels, embed_channels)
                )
                self.value = nn.Sequential(
                    nn.LayerNorm(embed_channels), nn.Linear(embed_channels, embed_channels)
                )
                self.proj = nn.Linear(embed_channels, text_channels)
        
                self.image_pools = nn.LayerList(
                    [nn.AdaptiveMaxPool2D((pool_size, pool_size)) for _ in range(num_feats)]
                )
        
            def forward(self, text_features, image_features):
                B = image_features[0].shape[0]
                assert len(image_features) == self.num_feats
                num_patches = self.pool_size**2
                mlvl_image_features = [
                    pool(proj(x)).view([B, -1, num_patches])
                    for (x, proj, pool) in zip(
                        image_features, self.projections, self.image_pools
                    )
                ]
                mlvl_image_features = paddle.transpose(
                    paddle.concat(mlvl_image_features, axis=-1), perm=[0, 2, 1]
                )
                q = self.query(text_features)
                k = self.key(mlvl_image_features)
                v = self.value(mlvl_image_features)
        
                q = q.reshape([B, -1, self.num_heads, self.head_channels])
                k = k.reshape([B, -1, self.num_heads, self.head_channels])
                v = v.reshape([B, -1, self.num_heads, self.head_channels])
        
                q = paddle.transpose(q, perm=[0, 2, 1, 3])
                k = paddle.transpose(k, perm=[0, 2, 1, 3])
                attn_weight = paddle.matmul(q, k)
        
                attn_weight = attn_weight / (self.head_channels**0.5)
                attn_weight = F.softmax(attn_weight, axis=-1)
        
                v = paddle.transpose(v, perm=[0, 2, 1, 3])
                x = paddle.matmul(attn_weight, v)
                x = paddle.transpose(x, perm=[0, 2, 1, 3])
                x = self.proj(x.reshape([B, -1, self.embed_channels]))
                return x * self.scale + text_features
        ```
        
    3.  Re-parameterization

        为什么这个模块叫 Re-parameterizable Vision-Language PAN 捏，在 Prompt-then-detect paradigm 小节中也提到了可以将离线词表重参数化为 Vision-Language PAN 层的参数。当推理的词表是固定的时候，此时 text encoder 的输出是固定的，即 $W \in R^{C'\times D}$，C&rsquo;是离线词表的大小（即文本个数），D 是 embedding 的维度。此时可以对 T-CSPLayer 和 I-Pooling Attention 层进行重参数化。
        
        1.  T-CSPLayer 的重参数化
      
            原 T-CSPLayer 可以表示为：
            $$X_l^{\prime}=X_l \cdot \delta\left(\max _{j \in\{1 . . C\}}\left(X_lW_j^{\top}\right)\right)^{\top}$$
            
            此时希望可以不再维护文本特征而由于此时的 W 是固定的，可以将其 reshape 成 $W \in R^{C'\times D \times 1 \times 1}$ 随后作为 $1\times1$ 卷积或 linear 层的权重。重参数化后该层可以表示如下：
            
            $$X\_l^{\prime}=X\_l \cdot \delta\left(\max \_{j \in\{1 . . C\}}\left(Conv\left(X\_l, W\_j\right), dim=1 \right) \right)^{\top}$$
            
            其中输出为 $X'_{l} \in R^{B \times D \times H \times W}$，conv(x,w) 表示以 w 为权重对 x 进行卷积操作。
        
        2.  I-Pooling Attention 的重参数化
    
            这里有点难绷，论文中给出的重参数化后的公式显然有问题
            
            ![img](https://private-user-images.githubusercontent.com/93063038/336705136-dc691c07-529f-4bc9-8d79-0f1f76fe94b8.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTc1Njc0MjMsIm5iZiI6MTcxNzU2NzEyMywicGF0aCI6Ii85MzA2MzAzOC8zMzY3MDUxMzYtZGM2OTFjMDctNTI5Zi00YmM5LThkNzktMGYxZjc2ZmU5NGI4LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MDUlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjA1VDA1NTg0M1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWMyMTZmMmQ0NjRhNGJlZjBhM2JmYTY3YzJjOGU0M2VmNWUwMGFlNjYyYzNlODJhOTVlMzFhODkzZmVhNDA2MmYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.LAbS2fiQaX0-WwVfU3lovxYzz1e4LoWnhaSiD6THApM)
            
            呀？左括号呢，dim=-1 是针对哪个操作...
            这儿应该也是与 T-CSPLayer 一样将文本特征部分重参数化为卷积或者 linear 层（？），毕竟其中涉及 W 的操作都是与 X 做矩阵乘法。（官方代码仓库暂时也没有公布重参数化相关的代码）
3.  Head

    在 YOLOv8 中 head 部分采用了解耦的检测头，分别用于预测类别（分类）和边界框（回归）。YOLO-World 也使用了类似的解耦检测头，但它不再做类别预测的分类任务，而是用于获取 object embedding。通过解耦检测头得到 object embedding 与边界框，随后，通过文本对比头（text contrastive head）得到 object embedding 与文本特征的相似度。

<a id="orgd6d582b"></a>

### Loss

totle loss 如下：

$$\mathcal{L}(I)=\mathcal{L}_{\text {con }}+\lambda_I \cdot(\mathcal{L}\_{\text {iou}}+\mathcal{L}\_{\mathrm{dff}})$$

其中 $\mathcal{L}_{\text {con }}$ 是针对语义的 region-text 对比损失，通过对 object-text（region-text）的相似性和 object-text assignments (使用 TOOD 中的 task-aligned label assignment 得到) 做交叉熵构建。 $\mathcal{L}\_{\text {iou}}$ 与 $\mathcal{L}\_{\mathrm{dff}}$ 是针对 boundingbox 的损失(与 yolov8 相同)。


<a id="org78433b0"></a>

## Result

<a id="orgf4b6832"></a>

### zero-shot capability

![img](https://github.com/PaddlePaddle/PaddleMIX/assets/93063038/9e71d97b-5353-4c4f-b016-44f2722b75fe.png)

在 LVIS 数据集上展现出了超越 DetCLIP、Grounding DINO 等方法的 zero-shot 能力，且具有更快的速度。


<a id="orgcbe359d"></a>

## Contribution
1.  提出了高效的实时开放词汇集目标检测算法 YOLO-World。
2.  提出 Re-parameterizable Vision-Language PAN 连接视觉与语言特征以及 region-text 的对比预训练的模式。
3.  提出 prompt-then-detect 的范式，配合 RepVL-PAN 提升了推理速度。
4.  表现出了强大的 zero-shot 能力并在 LVIS 数据集上达到了 35.4 AP 和 52.0 的 FPS.

![img](https://github.com/PaddlePaddle/PaddleMIX/assets/93063038/08729efe-d74f-4419-8d76-3025d9cc250b.png)

