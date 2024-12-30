### 姓名

王译辉（mori0umi）

### 开发中的快乐开源任务

PIR-TensorRT converter推全升级
Paddle Tensor 规范化二期

### 本双周工作

1. **Paddle Tensor 规范化二期**
   - 提交一个PR
      - https://github.com/PaddlePaddle/Paddle/pull/70146

2. **PIR-TensorRT convert**
   - 完成两个PR
      - https://github.com/PaddlePaddle/Paddle/pull/69706
      - https://github.com/PaddlePaddle/Paddle/pull/69705

   - 提交一个PR
      - https://github.com/PaddlePaddle/Paddle/pull/70066

3. **问题疑惑与解答**

   - 问题 a：完成 Tensor 规范化二期任务的过程中，对 C++ 模板编程不熟悉，出现了许多报错。

   ​       答：勤于从互联网上寻找资料学习，总结问题出错的原因，在这个过程中逐渐掌握相关技能。

   - 问题 b：Tensor RT converter 任务运行 py 测试文件，报段错误。

   ​       答：Converter 编写有误，未考虑到动态 shape 的问题，修正后报错消失。

   - 问题 c：完成 Tensor 规范化二期任务的过程中，遇到了两难问题：模板函数无法偏特化处理，模板类无法注册 Kernel。

   ​       答：参考已有实现，发现可以用模板函数进行转发，实现逻辑由重载括号运算符的 Functor 模板类编写。

### 未来双周计划

1. 模型复现任务：尝试 Paddle Mix 模型复现任务
2. 继续完善 converter 推全升级任务、Tensor 规范化任务

