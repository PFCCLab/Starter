### 姓名

钟浩元

### 开发中的快乐开源任务

PaddleMIX 快乐开源活动 (2025 H1) #1046
NO.7 DocOwl2 模型推理

### 本双周工作

1. **任务 - PaddleMIX 快乐开源活动 (2025 H1) #1046 NO.7 DocOwl2 模型推理**
   - 学习了教程：基于 PaddleMIX 实现 MiniCPM-V-2_6 多模态模型推理
   https://aistudio.baidu.com/projectdetail/9013948?forkThirdPart=1
   - 快乐开源活动 (2025 H1) #1046 NO.7 DocOwl2 模型推理
   - 根据教程尝试对 DocOwl2 模型做权重转换。仍在尝试中。

3. **问题疑惑与解答**

   - 在将基于 pytorch 的模型迁移到 paddle 平台上实现过程中遇到了许多问题。例如：
     1. 不知道我模仿教程中做的权重转换是否正确
     2. 不知道 huggingface 中 DocOwl2 是如何在 pytorch 上如何实现的。其 huggingface 页面中有一个 quickstart，还没有尝试跑通。这可能导致对模型理解不够，就算将此模型在 paddle 平台上跑通，也只能说是凑巧。（https://huggingface.co/mPLUG/DocOwl2）
     3. 遇到了 TypeError: LlamaTokenizer.**init**() missing 1 required positional argument: 'vocab_file'。这显示我缺少了一个文件，但是我已经将 DocOwl2 在 huggingface 页面的所有文件都下载下来了，原本就没有 vocab_file。这个报错不知道怎么解决。

### 未来双周计划

- 继续完成 PaddleMIX。
- 希望找到一个合适教程或者样例指导
