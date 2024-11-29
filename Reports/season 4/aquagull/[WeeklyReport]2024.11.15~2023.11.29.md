### 姓名

何泓域

### 开发中的快乐开源任务

1.新增 paddle.linalg.svdvals
2.新增 paddle.to_tensor针对实现了__cuda_array_interface__接口的数组对象(如torch.Tensor)进行适配

### 本双周工作

1. **任务：新增 paddle.linalg.svdvals 算子**

   - 已完成 paddle.linalg.svdvals 算子的 CPU 和 GPU 内核实现，包括前向计算和反向梯度计算。
   - 解决了批量计算时 x_grad 形状不匹配的问题，该问题是 由于反向算子中调用SvdKernel的full_matrices参数错误传递以及 Diag 函数在批量情况下使用不当导致的。 最终通过修改 full_matrices 参数，并使用 diag_embed 函数正确构建批量对角矩阵解决了该问题。

   - 已结束此任务

2. **任务 新增适配_cuda_array_**

   - 尚未开始

3. **问题疑惑与解答**

   - 问题: 暂无

     答：xxx

### 未来双周计划

1. 完成 paddle.to_tensor 针对 __cuda_array_interface__ 的适配工作，并添加相应的测试用例。
2. 参加其他任务，继续学习