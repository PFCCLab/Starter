### 刘煦东

2024.08.24-2024.09.06

### 开发中的快乐开源任务

CINN 编译器符号推导扩量

### 本双周工作

1. **任务 2：CINN 编译器符号推导扩量**

   - 描述：合入 5 个复杂难度 op 算子接口的 PR，3 个复杂难度 op 算子的 PR 等待 CI 测试，修复 unary_infer_sym.cc 中多余 data 问题的 PR 已合入。
   - PR链接：
    1. `warpctc` https://github.com/PaddlePaddle/Paddle/pull/67539/ 已合入
    2. `warprnnt` https://github.com/PaddlePaddle/Paddle/pull/67567 已合入
    3. `deformable_conv` https://github.com/PaddlePaddle/Paddle/pull/67581 已合入
    4. 修复 unary_infer_sym.cc 中多余 data 问题 https://github.com/PaddlePaddle/Paddle/pull/67642 已合入
    5. `max` https://github.com/PaddlePaddle/Paddle/pull/67713 已合入
    6. `matrix_nms` https://github.com/PaddlePaddle/Paddle/pull/67607 已合入
    7. `cinn_op.pool2d` https://github.com/PaddlePaddle/Paddle/pull/67826 CI 中
    8. `unsqueeze` https://github.com/PaddlePaddle/Paddle/pull/67916 CI 中
    9. `triangular_solve` https://github.com/PaddlePaddle/Paddle/pull/68022 CI 中

2. **问题疑惑与解答**

   - 问题 1：在 CINN 符号推导流程中 git clone 和 cmake 失败。

     答：git clone 失败，是因为没有设置 git 代理；cmake 需要关闭代理。

   - 问题 2：一些特殊的数据可能有多个获取来源，如 operand_source 和 attributes。

     答：需要进行多重判断来获取数据。

   - 问题 3： cinn_op.pool2dop 算子的接口实现 pool2d 算子已经在 unary_infer_sym.cc 中有实现。

     答：直接将 unary_infer_sym.cc中的函数实现引用过来即可，避免大量代码的粘贴。


### 未来双周计划

1. 完成 CINN 编译器符号推导扩量剩余 PR;
2. 阅读 CINN 后端工作介绍文档，对后端任务进行初步了解。