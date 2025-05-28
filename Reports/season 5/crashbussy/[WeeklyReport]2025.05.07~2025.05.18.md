### 姓名

钟浩元

### 开发中的快乐开源任务

[0-size Tensor No.343, 350, 351] Add 0-size Tensor support for paddle.tril paddle.Tensor.tril paddle.triu API. #72814
https://github.com/PaddlePaddle/Paddle/pull/72814/files

### 本双周工作

1. **任务 - 【开源任务】 Paddle API 0-size 机制建设 #72637**

   - [0-size Tensor No.318] Add 0-size Tensor support for paddle.Tensor.matmul API. #72780
   - 已经完成任务，提交了pr。正在等待通过
   - PaddleAPITest 有报错信息。日志所在的路径：
PaddleAPITest/report/0size_tensor_gpu/20250319/compare_with_torch/coredump_error/error_log.log
paddle/phi/kernels/impl/tril_triu_kernel_impl.h 中TriuKernel TrilKernel 并无法很好的支持0 size Tensor。当遇到0 size Tensor时没及时返回导致GPU版本的实现中launch了cuda kernel，进而出现cuda error 9 这个报错。
完成了5个文件的修改。按照要求增加了单测
![image](https://github.com/user-attachments/assets/c06132fe-8508-49f4-b925-d9036fa4b3dc)

已经成功合入。


2. **问题疑惑与解答**

   无

