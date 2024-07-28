### 姓名

冯屹芃

### 开发中的快乐开源任务

1. PIR单测推全
2. 为公开 API 标注类型提示信息（文档打卡）
3. 报错日志体系优化

### 本双周工作

1. **任务 PIR单测推全**

   - 提交4个PR，合入3个PR
   - 合入PR链接：
     1. https://github.com/PaddlePaddle/Paddle/pull/66285
     2. https://github.com/PaddlePaddle/Paddle/pull/66286
     3. https://github.com/PaddlePaddle/Paddle/pull/66288

2. **任务 标注类型提示信息**

   - 提交1个PR并合入
   - 合入PR链接：
     https://github.com/PaddlePaddle/Paddle/pull/66328

3. **任务 报错日志体系优化**

   - 提交5个PR

4. **问题疑惑与解答**

   - 在PIR的libpaddle.pir.Value类型里，没有desc相应的接口

     答：在desc前添加分支if not paddle.framework.use_pir_api():

   - libpaddle.Tensor是动态图的逻辑，被传入了处理静态图的函数方法

     答：提前建立条件分支。


### 未来双周计划

1. 继续完成报错日志体系优化任务
2. 开始上手编译器符号扩量任务
