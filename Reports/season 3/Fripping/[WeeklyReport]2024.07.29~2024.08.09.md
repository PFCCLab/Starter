### 姓名

冯屹芃

### 开发中的快乐开源任务

1. CINN编译器符号扩量任务
2. 报错日志体系优化
3. PEP标准集合泛型支持升级
4. Ruff新rule引入

### 本双周工作

1. **任务 CINN编译器符号扩量任务**

   - 合入1个PR(3个算子)
   - 合入PR链接：
     https://github.com/PaddlePaddle/Paddle/pull/66896

2. **任务 报错日志体系优化**

   - 合入9个PR(共112个问题宏）
   - 合入PR链接：
     1. https://github.com/PaddlePaddle/Paddle/pull/66534
     2. https://github.com/PaddlePaddle/Paddle/pull/66578
     3. https://github.com/PaddlePaddle/Paddle/pull/66594
     4. https://github.com/PaddlePaddle/Paddle/pull/66615
     5. https://github.com/PaddlePaddle/Paddle/pull/66632
     6. https://github.com/PaddlePaddle/Paddle/pull/66715
     7. https://github.com/PaddlePaddle/Paddle/pull/66777
     8. https://github.com/PaddlePaddle/Paddle/pull/66784
     9. https://github.com/PaddlePaddle/Paddle/pull/66799

3. **任务 PEP标准集合泛型支持升级**

   - 合入5个PR(共50个文件）
   - 合入PR链接：
     1. https://github.com/PaddlePaddle/Paddle/pull/67069
     2. https://github.com/PaddlePaddle/Paddle/pull/67131
     3. https://github.com/PaddlePaddle/Paddle/pull/67133
     4. https://github.com/PaddlePaddle/Paddle/pull/67144
     5. https://github.com/PaddlePaddle/Paddle/pull/67146

4. **Ruff新rule引入**

   - 提交2个PR(共18个文件）

5. **问题疑惑与解答**

   - hsigmoid算子的infermeta文件中只写了1个输出，实际上ops.yaml上对hsigmoid的描述是一共有3个输出

     答：根据官方API文档描述，补充其余两个输出张量的形状

   - PADDLE_ENFORCE输入数据类型问题

     答：根据程序上下文正确推断CHECK对象的数据类型，并添加相应的约束和报错信息
  
   - PR提交后conflict
  
     答：没什么特别好的办法，只能及时更新分支以及发生冲突后尽快解决


### 未来双周计划

1. 继续完成编译器符号扩量任务
2. 继续完成Ruff新rule引入检查任务