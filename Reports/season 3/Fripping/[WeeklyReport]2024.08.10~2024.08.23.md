### 姓名

冯屹芃

### 开发中的快乐开源任务

1. CINN编译器符号扩量任务
2. 报错日志体系优化

### 本双周工作

1. **任务 CINN编译器符号扩量任务**

   - 提交4个PR(9个算子)，合入其中2个PR（5个算子）
   - 合入PR链接：
     1. https://github.com/PaddlePaddle/Paddle/pull/67037
     2. https://github.com/PaddlePaddle/Paddle/pull/67390

2. **任务 报错日志体系优化**

   - 提交1个PR(共115个问题宏）
   - PR链接：
     https://github.com/PaddlePaddle/Paddle/pull/67657

3. **问题疑惑与解答**

   - rnn算子的infermeta文件中只写了2个输出，实际上ops.yaml上对其的描述是一共有4个输出，且API文档也没有很好的描述

     答：根据kernel文件描述与OpTest单测文件进行推测，补充其余两个输出张量的形状

   - PADDLE_ENFORCE报错信息类更新报错问题（phi::errors to common::errors）

     答：common::errors命名空间与cinn::common重复，因此在修改cinn路径下的文件需要改为::common::errors



### 未来双周计划

1. 继续完成编译器符号扩量任务
2. 尝试接手新的社区开源任务
