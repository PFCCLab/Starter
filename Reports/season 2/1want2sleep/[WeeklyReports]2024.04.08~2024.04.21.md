### 姓名

董黄莹

### 开发中的快乐开源任务

PPSCI 为 PaddleScience 案例添加 export 和 inference 功能 No.25

### 本双周工作

   - 助力PPSCI api文档项目结项

3. **问题疑惑与解答**

   - 问题 单独启动分布式相关代码很顺利，但是doctest会有问题，添加 # doctest: +REQUIRES(env:GPU, env:DISTRIBUTED) 报错 ValueError: line 11 of the doctest for misc.all_gather has an invalid option: '+REQUIRES(env:GPU'；dist.init_parallel_env() 添加 # doctest: +SKIP 报错RuntimeError: The global group is not initialized.为什么？

     答：# doctest: +REQUIRES(env:GPU, env:DISTRIBUTED)这个语法是给xdoctest使用的，pdsci用的是pydoctest，无法感知这种语法。dist.init_parallel_env()是有返回值的，需要用变量接一下。想跳过某一行的执行，得用：  # doctest: +SKIP， 并不是仅仅跳过输出。

### 未来双周计划

1. 继续 PaddleScience 案例添加 export 和 inference 功能。
