### 姓名

文以恒（kineast）

### 开发中的快乐开源任务

PIR-TensorRT converter推全升级

### 本双周工作

1. **Paddle Tensor规范化**
   - 提交1个PR，已成功合入
     - https://github.com/PaddlePaddle/Paddle/pull/69542
2. **PIR-TensorRT convert**
   - 提交2个PR，但做了3个，其中有一个中途取消
     - https://github.com/PaddlePaddle/Paddle/pull/69718
     - https://github.com/PaddlePaddle/Paddle/pull/69871
3. **API图例添加**
   - 提交1个PR，等待review
     - https://github.com/PaddlePaddle/docs/pull/6967
4. **Paddle算子规范化标注**
   - 已完成52个算子规范化的标注工作
5. **问题疑惑与解答**

   - 问题 a：file too short.这个报错。

   ​       答：需要在bashrc中添加相关的export配置，export LD_LIBRARY_PATH=/usr/local/TensorRT路径(比如TensorRT-8.6.1.6)/lib

   - 问题 b：在遇到tensorRT能否无条件进入converter时不能认真判断

   ​       答：有部分算子在某些情况下是无条件进入，但部分情况下的限制条件需要仔细判断，比如我做的take_along_axis算子

### 未来双周计划

1、继续修改TensorRT converter推全的修改
2、尝试开始Paddle Mix的相关任务

