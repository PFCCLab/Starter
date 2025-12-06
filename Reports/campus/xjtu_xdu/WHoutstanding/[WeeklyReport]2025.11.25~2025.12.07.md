### 姓名

王豪

### 开发中的快乐开源任务

【HACKATHON 预备营】飞桨启航计划集训营（社团版）[#76500](https://github.com/PaddlePaddle/Paddle/issues/76500#issuecomment-3580683155)

### 本双周工作

1. **📝 文档示例代码修复**
[CodeStyle][Xdoctest][17,21,27,28] Fix example code(paddle.Tensor.matmul,paddle.Tensor.new_empty,paddle.Tensor.sgn,paddle.Tensor.shape) [#13553](https://github.com/PaddlePaddle/Paddle/pull/76691)

为如下 API 修复示例代码
paddle.Tensor.matmul
paddle.Tensor.new_empty
paddle.Tensor.sgn
paddle.Tensor.shape

目前已提交 PR，CI测试有问题，还在修改。
2. **完成 Paddle 本地编译**
实现了从 Windows 下对Paddle源码进行编译，已成功完成任务并发送邮件。

3. **Stable-Diffusion 训练推理**
使用AI Studio完成了大模型文生图模型Stable-Diffusion训练推理打卡，已成功完成任务并发送邮件。

4. **PaddlePaddle PHI算子库CUDA Kernel规范化**
已报名增添paddle/phi/kernels/gpu/weighted_sample_neighbors_kernel.cu头文件。
目前已经完成头文件的新增，准备提交 PR。
5. **【GraphNet 新手任务】计算图收集**
已经提交 PR [New Sample] Add "fcn_restnet50" Model Computational Graph [#417](https://github.com/PaddlePaddle/GraphNet/pull/417)
正在等待 PR 合入。
6. **问题疑惑与解答**

   - 问题 似乎没找到paddle.Tensor.matmul的定义？

     答："matmul", 里面，示例代码也在里面，但是看着好像已经改过了，你可以本地试一下有没有问题。为什么在这，和图上那个工作有关。

   - 问题 问题：报名的paddle/phi/kernels/gpu/weighted_sample_neighbors_kernel.cu头文件已被添加？

     答：可以再看下PaddleCustomDevice仓库中需要用到对应头文件的代码，有可能Paddle仓库的头文件缺少部分函数声明


### 未来双周计划

1. Review [CodeStyle][Xdoctest][17,21,27,28] Fix example code(paddle.Tensor.matmul,paddle.Tensor.new_empty,paddle.Tensor.sgn,paddle.Tensor.shape) [#13553](https://github.com/PaddlePaddle/Paddle/pull/76691) 通过CI并合入。
2. 尝试 PaddlePaddle API 兼容性增强任务。
