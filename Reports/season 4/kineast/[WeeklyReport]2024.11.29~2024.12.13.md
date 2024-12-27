### 姓名

文以恒（kineast）

### 开发中的快乐开源任务

1. 为 Tensor API 文档增加图例 
2. Paddle Tensor规范化二期任务
3. PIR-TensorRT converter推全升级

### 本双周工作

1. **Paddle Tensor规范化二期**
   - 提交2个PR，已成功合入1个
     - https://github.com/PaddlePaddle/Paddle/pull/70024
     - https://github.com/PaddlePaddle/Paddle/pull/70200
2. **PIR-TensorRT convert**
   - 提交1个PR，已经approve，等待合入
     - https://github.com/PaddlePaddle/Paddle/pull/70170
3. **API图例添加**
   - 提交1个PR，已合入
     - https://github.com/PaddlePaddle/docs/pull/6967
4. **问题疑惑与解答**

   - 问题 a：模版函数无法实现偏特化

   ​       答：可以单独写一个更加顶层的kernel去调用本来的函数，这样就解决了结构体不能注册，函数不能偏特化的问题


### 未来双周计划

1、继续修改TensorRT converter推全的修改
2、继续修改Tensor规范化二期的相关任务

