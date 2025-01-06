### 姓名

张俊杰（PolaKuma）

### 开发中的快乐开源任务

tensor规范化第二期任务

### 本双周工作

1. **Paddle Tensor规范化第二期**
   - 提交两个PR，已成功合入一个
     - https://github.com/PaddlePaddle/Paddle/pull/69996
     - https://github.com/PaddlePaddle/Paddle/pull/70094
2. **PaddleScience Export任务**
   - 提交两个PR，已成功合入
     - https://github.com/PaddlePaddle/PaddleScience/pull/1036
     - https://github.com/PaddlePaddle/PaddleScience/pull/1030
3. **CINN编译器后端Pass注释添加**
   - 提交一个PR
     - https://github.com/PaddlePaddle/Paddle/pull/70213
4. **问题疑惑与解答**

   - 问题 a：NAN的问题：写单测时候nan是匹配上的，但是单测说mismatch，输出结果又没问题。

   ​       答：通过请教同事，这个单测用的是assert_allclose，allclose的计算公式是作差、乘法再比较，而nan是不能用作差来算的。单独写一个单测用array_equal来测。

   - 问题 b：也是inf和nan：windows上的vs编译器对于std;:isnan、isinf这种只能接受浮点数作为输入，否则会报错

   ​       答：参考isfinite_kernel.h，将int类型的通过模板的SFINEA技术来解决。

   - 问题 c：某个Converter算子疑问：写anchor_generator的converter时候，单测需要调用这个函数，但是这个api被移除了，只保留了plugin的实现，导致前期浪费很多时间在上面。迁移fluid的PR：https://github.com/PaddlePaddle/Paddle/pull/65590/files#diff-f4daa2300ccaef2d26d676fdbe90ec895a1ba1a83236f1a9e6b613c6dca4adfe ；之后重新写了逻辑，但是仍然报错，检查函数逻辑觉得差不多，其中x是预期输出的out_anchor，y是预期输出的out_var，然而好像对比时不太对，交换输出顺序仍然这样报错。

   ​       答：提了个PR，待好心人拉取一下看看。https://github.com/PaddlePaddle/Paddle/pull/69905

   - 问题 d：版本问题：PaddleScience那边amgnet_cylinder.py和cfdgcn.py里面有用pgl库，但是import pgl报错：pgl还在用paddle.fluid被迁移的算子（我看pgl有一年没更新了）。

   ​       答：通过请教同事，vim过去改掉paddle.framework.core，或者降级Paddle为2.5版本。

### 未来双周计划

1. 模型复现任务：尝试学习模型复现任务
2. 尝试继续推进tensor规范化第二期任务，目前存在卡顿

