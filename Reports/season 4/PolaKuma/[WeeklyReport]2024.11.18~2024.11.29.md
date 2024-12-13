### 姓名

张俊杰（PolaKuma）

### 开发中的快乐开源任务

PIR-TensorRT converter推全升级

### 本双周工作

1. **Paddle Tensor规范化**
   - 提交三个PR，已成功合入
     - https://github.com/PaddlePaddle/Paddle/pull/69361
     - https://github.com/PaddlePaddle/Paddle/pull/69477
     - https://github.com/PaddlePaddle/Paddle/pull/69301
2. **PIR-TensorRT convert**
   - 提交三个PR，已成功合入一个，待合入一个
     - https://github.com/PaddlePaddle/Paddle/pull/69848
     - https://github.com/PaddlePaddle/Paddle/pull/69563
     - https://github.com/PaddlePaddle/Paddle/pull/69751
3. **问题疑惑与解答**

   - 问题 a：在提交过多PR的情况下，单测可能未考虑全面，导致问题较多。由于对进入TRT的类型理解不够清晰，review时出现了较多问题，影响了进度。

   ​       答：在提交前加强对单测的覆盖率检查，并深入理解进入TRT的类型。

   - 问题 b：因为对TRT概念理解不清晰，导致前期debug做了许多无用功。例如：遇到"The last op of converter pir Program in test must be split op that is the next of of pd_op.engine"的问题。

   ​       答：通过请教同事，发现是条件写错的问题，修改后成功解决。

   - 问题 c：遇到了将input_tensor判断为bool时的错误，文档显示add_unary应输出bool，但直接返回layer_output会报错。

   ​       答：尽管暂未完全解决，但发现加上print(layer_output.dtype)或其他与layer_output.dtype相关的无意义代码后，错误消失。

   - 问题 d：对某些算子（如TanhShrink）的限制条件理解不足，未在op_teller.cc中看到限制，只在act_op_list中找到。

   ​       答：通过导师的帮助，逐渐加深对这些限制条件的理解。

### 未来双周计划

1. 模型复现任务：尝试学习模型复现任务，把文档写了
2. 尝试推进CINN编译器后端Pass改造任务

