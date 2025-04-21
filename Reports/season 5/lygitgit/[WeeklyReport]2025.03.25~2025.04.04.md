### 姓名

刘易

### 开发中的快乐开源任务

PaddleMIX 快乐开源活动 (2025 H1) No.24 多模态生成-SD3特色应用

### 本双周工作

1. **任务 - 热身打卡**

   - 完成 文档打卡任务
   - 正在进行ddle 本地编译打卡任务（在win下载docker但还未完成编译）
   - 完成 Stable-Difussion 训练推理打卡任务


2. **任务 - 多模态生成-SD3特色应用**

   - 以小说转漫画为实现的应用，初步完成ipynb代码的编写
     1. 大语言模型获取漫画的分页信息和绘制的描述词
     2. 文生图模型进行漫画编写
     3. 查找并尝试添加可人为调整漫画的图像编辑功能

   - 基于需求尝试多个pipline，并查看图像编辑StableDiffusionInpaintTask的代码逻辑，后续进行相关添加:
     1. StableDiffusionPix2PixZeroPipeline给的示例bug较多，修正后效果并不好
     2. 查看latent的使用，且如何与mask配合，进行文本和图像指导的生成

3. **问题疑惑与解答**

   - 问题 a 我想调用"ernie-4.5-8k-preview"的API，开始可以使用（可能是因为我一年前用过，充过钱的原因吗），但后来报错'token 已经用完毕，请充值后使用'，发现如果充钱的话一次要冲好多，不像之前充个一块钱就能用吗？用部署的蒸馏版的deepseek啥的效果都不太好，能少充一点去用"ernie-4.5-8k-preview"嘛？

     答：xxx

   - 问题 b 借鉴StableDiffusionPix2PixZeroPipeline注释里的案例，给出Pipline参数是懒加载，但_C_ops.fill_(x, value)并不能为没有分配内存的x进行赋值，即使调整赋值的部分后续也还有一连串报错，这个懒加载的功能是不是不能用呀？（我找了好久原因QAQ）

     答：xxx

### 未来双周计划

1. 完成应用初步的gradio和ipynb
2. 尝试添加人为干预进行漫画编辑（图像编辑功能）
