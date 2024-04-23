### 姓名

李逸清（sayoriaaa）

### 开发中的快乐开源任务

复数数据类型扩展

### 本双周工作

1. **热身打卡任务**

   -  ✅ 在linux服务器上完成 Paddle 本地编译。

2. **[复数任务](https://github.com/PaddlePaddle/Paddle/issues/61975)**

    - 编写`Floor`算子，并进行测试。

### **问题疑惑与解答**

   - 问题：已在_C_ops中注册，但测试时显示没有注册。

     答：考虑编译版本是否与测试版本相同。后续发现是服务器上pull更新失败。

  - 问题：原paddle的floor()函数是定义在哪里？paddle源码中没有看到相关实现。

    答：基于Eigen的内部实现。

  - 存在问题：不建议把floor算子变成complex类的成员函数，建议在`activation_functor`中完成修改。

### 未来双周计划

1. 继续完成任务17 `Floor`算子对复数的支持。


