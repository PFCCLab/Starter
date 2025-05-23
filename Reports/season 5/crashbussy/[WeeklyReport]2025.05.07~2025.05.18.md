### 姓名

钟浩元

### 开发中的快乐开源任务

【开源任务】 Paddle API 0-size 机制建设 #72637
NO.318 paddle.Tensor.matmul对0-size Tensor的支持

### 本双周工作

1. **任务 - 【开源任务】 Paddle API 0-size 机制建设 #72637**

   - [0-size Tensor No.318] Add 0-size Tensor support for paddle.Tensor.matmul API. #72780
   - 已经完成任务，提交了pr。正在等待通过
   - 在PaddleAPITest report/0size_tensor中检索paddle.Tensor.matmul的错误日志，发现[accuracy error]报错。
   - 分析可能是前向过程出错。！！！注意到(shapes (0, 100, 1, 40), (0, 100, 40) mismatch)，也是就shape不匹配的问题。

2. **问题疑惑与解答**

   无

