### 姓名

董黄莹

### 开发中的快乐开源任务

PPSCI Doc No.66-74 已经提了PR并按照Review进行了修改

### 本双周工作

   - 完成了所有热身打卡任务（文档、编译、大模型、paddlescience的安装和VIV例程）
   - PPSCI Doc No.38-40 已经合入


3. **问题疑惑与解答**

   - 问题 learnable_parameters.append()是不是可以给elastic增添可学习参数？

     答：PDE类是跟sympy符号化计算绑在一起的，如果对elastic这类的在PPSCI中不带有可学习参数的方程用learnable_parameters.append()方法，只是形式上在它的learnable parameter里面存储了，并不能实际参与网络计算。其实想支持也很简单，就是跟viv（目前只有viv有可学习参数）一样的做法，通过某种指定的形式，让计算机知道E和mu是可学习参数，而不是一个常量，然后elastic这个公式会在solver里从符号公式转换为函数，训练的时候自动就会让E和mu参与计算了。

   - 问题 有些机理公式在实际作用中可能不准，比如缺了高阶项。如果elastic这类方程能支持增添可学习参数的话，是不是可以在机理公式的基础上增加一个未知的可学习项，然后慢慢拟合高阶项？比如控制领域一般用代理模型去建模控制对象，但是随着控制对象的发展（比如用了新型材料、变成复杂的刚柔耦合机构……），实际控制对象的模型会复杂很多，但是建模的时候没法用精确的机理模型表示，这个时候可以假设代理模型和真实模型之间缺了一个高阶项（或者别的什么未知项），然后去学习这个差距项，是不是可以让模型更准？

     答：是可以的，而且这种手动引入了缺少高阶的先验可能比直接让模型自己学效果会更好。

   - 问题 为什么修改state_dict里面的tensor值只能精确到小数点后第六位？显示到小数点后第八位，但是第七和第八位完全控制不住。比如如果是float -3.1就是-3.1，to_tensor之后-3.1就会显示为-3.09999990。

     答：浮点数转换可能有一些误差，不影响实际使用的。paddle.set_default_dtype("float64")，先执行一下这个，然后精度可能能高一些。

   - 问题 调用ppsci.geometry.TimeXGeometry.uniform_points()方法的时候，报错TimeDomain没有num_stamps，我看了一下代码，发现TimeDomain的init里面没有num_timestamps，但是加进去也不管用。

     答：得先指定time_step或者timestamps，根本原因是这个代码没有做好充分的入参检查，time_step和timestamps必须存在一个。

### 未来双周计划

1. 再做一下api docs的任务熟悉api的用法。
2. 尝试新任务 PaddleScience 案例添加 export 和 inference 功能。
