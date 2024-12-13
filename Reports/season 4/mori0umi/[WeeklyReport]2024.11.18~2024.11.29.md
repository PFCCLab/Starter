### 姓名

王译辉（mori0umi）

### 开发中的快乐开源任务

PIR-TensorRT converter推全升级

### 本双周工作
1. **Tensor图例文档任务**
   - 完成 Tensor.stack API 中英文文档图例的添加任务

2. **Paddle算子规范化**
   - 完成50个单测状态统计任务

2. **PIR-TensorRT convert**
   - 提交三个PR
     - https://github.com/PaddlePaddle/Paddle/pull/69706
     - https://github.com/PaddlePaddle/Paddle/pull/69594
     - https://github.com/PaddlePaddle/Paddle/pull/69705

3. **问题疑惑与解答**

   - 问题 a：定位问题能力不足，出现问题排查时做了很多无用功，如反复重新全量编译，浪费了很多时间。

   ​       答：勤于请教前辈，总结问题出错的原因，在这个过程中逐渐掌握任务解决流程。

   - 问题 b：Tensor RT converter 任务无法运行 py 测试文件，报错信息为动态链接库问题。

   ​       答：手动执行 export LD_LIBRARY_PATH=/usr/local/TensorRT-8.6.1.6/lib，并将其添加到.bashrc 文件中。

   - 问题 c：遇到了编译过程中显示 networkx 包未安装，pip 之后仍然显示同样错误。

   ​       答：指定固定版本的 pip 后得到解决。

   - 问题 d：运行 converter 测试文件时，出现报错，算子未能正确通过Makerpass。

   ​       答：重新编译，安装新的whl包后得到解决。

### 未来双周计划

1. 模型复现任务：尝试学习模型复现任务
2. 继续完善converter推全升级任务

