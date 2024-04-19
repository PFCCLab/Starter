### 姓名

陈泽宇 (InsaneOnion)

### 开发中的快乐开源任务

专项团：大模型套件

### 本双周工作

1. **完成Checkpoint Merger(已合入)**

2. **热身打卡任务**

   - 在 PaddleMIX 中跑通Stable-Diffusion 训练推理

3. **问题疑惑与解答**

    - 问题 a: 拉取模型参数时(未指定本地路径的情况下)，diffusers 使用 snapshot_download 函数实现一次性将 repo 中模型参数以及相关文件下载至本地。而 paddle 的模型参数 repo 存储在bos云盘中，且没有 snapshot_download 的替代函数实现(利用 hunggingface 提供的 HfApi 方法列出 repo 中的文件信息后逐个下载)。


     答：使用 DiffusionPipeline 的 from_pretrained 方法替代，同样能够实现拉去所有需要的模型参数以及配置文件。

### 未来双周计划

1. 新增模型open-sora
2. 完成热身打卡任务

