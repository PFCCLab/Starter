### 刘煦东

2024.08.10-2024.08.23

### 开发中的快乐开源任务

CINN 编译器符号推导扩量

### 本双周工作

1. **任务 2：CINN 编译器符号推导扩量**

   - 描述：合入 4 个中等难度、2 个复杂难度 op 算子接口的 PR，3 个复杂难度 op 算子的 PR 等待 CI 测试，修复 unary_infer_sym.cc 中多余 data 问题的 PR 等待 CI 测试。
   - PR链接：
    1. `one_hot,mean,lu,lu_unpack` https://github.com/PaddlePaddle/Paddle/pull/67206 已合入
    2. `unpool3d` https://github.com/PaddlePaddle/Paddle/pull/67494 已合入
    3. `viterbi_decode` https://github.com/PaddlePaddle/Paddle/pull/67499 已合入
    4. `warpctc` https://github.com/PaddlePaddle/Paddle/pull/67539/ CI 中
    5. `warprnnt` https://github.com/PaddlePaddle/Paddle/pull/67567 CI 中
    6. `deformable_conv` https://github.com/PaddlePaddle/Paddle/pull/67581 CI 中
    7. 修复 unary_infer_sym.cc 中多余 data 问题 https://github.com/PaddlePaddle/Paddle/pull/67642 CI 中

2. **问题疑惑与解答**

   - 问题 1：`InferMeta` 函数中存在错误，没有将所有输出参数都设置维度约束。

     答：需要通过算子更底层的 `Kernel` 函数实现分析出输出参数的维度信息。

   - 问题 2：在 `InferSymbolicShape` 中引入新符号之后，在编译过程中无法推导出相应的维度，会弹出报错。

     答：需要在 `OpTset` 文件中的 `test_check_output` 函数调用中关闭 `test_infer_sym` 。

   - 问题 3：不要随意引入新符号。

     答：很多时候在 `InferMeta` 函数中给出的是动态形状 `-1` ，但是通过阅读 `kernel` 代码可以提取出相应的维度信息。


### 未来双周计划

1. 合入 CINN 编译器符号推导扩量所有提交的 PR，阅读相关 CINN 符号推导整体流程文档。