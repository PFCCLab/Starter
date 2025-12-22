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

成功合入 PR

2. **PaddlePaddle PHI算子库CUDA Kernel规范化**
添加 paddle/phi/kernels/gpu/weighted_sample_neighbors_kernel.cu 源文件到编译列表：
backends/metax_gpu/CMakeLists.txt
PR 已经Review, 等待合入。
3. **【GraphNet 新手任务】计算图收集**
已经Review PR [New Sample] Add "fcn_restnet50" Model Computational Graph [#417](https://github.com/PaddlePaddle/GraphNet/pull/417)
正在等待 CI 测试和 PR 合入。
4. **PaddlePaddle API兼容性增强**
完成了 Paddle API自身修改，正在完成 Paddle 单测测试，准备提交 PR

5. **问题疑惑与解答**

   - 问题 等待 PR review的时间太长

### 未来双周计划
1.  完成 PaddlePaddle API 兼容性增强任务。