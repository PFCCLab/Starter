### 姓名

李逸清（sayoriaaa）

### 开发中的快乐开源任务

复数数据类型扩展

### 本双周工作

由于已经错过了正式报名时间（3/28报名并通过），因此实际工作实际恰好为一周。

1. **热身打卡任务**

   -  ✅ 修改飞桨文档：学习了飞桨 API 文档书写规范以及中英文文档对应法则，提交了文档修复的 pr ：[6540](https://github.com/PaddlePaddle/docs/pull/6540)（报名前已完成）

   -  ⏳ 完成 Paddle 本地编译：配置了linux下的相关环境，但由于网络问题暂能下载全部submodule。

   -  ✅ Stable-Diffusion 训练推理：利用 AI Studio v100 完成了 Stable-Diffusion 的训练推理任务。发现文档中直接使用`git clone`的默认`develop`分支存在问题，指定分支`release/1.0`可以正常运行。

2. **[复数任务](https://github.com/PaddlePaddle/Paddle/issues/61975)**

    - 详细阅读示例[PR](https://github.com/PaddlePaddle/Paddle/pull/55380)，个人理解如下：
      1. 首先，复数数据类型扩展的对象是算子，因此算法的核心需要对`paddle/phi`下的文件进行修改。
        - 前向的逻辑在`common/complex.h`中通过模板定义，以同时支持不同的复数类型。
        - 由于paddle是深度学习框架，因此我们还需要在`kernels/funcs/activation_functor.h`中定义这些算子的梯度（需要编写CPU和GPU的函数），然后分别在`kernels/cpu`和`kernels/gpu`中进行注册。由于复数的梯度计算比较复杂，需要参考[实函数的微分](https://github.com/PaddlePaddle/community/blob/master/pfcc/paddle-code-reading/complex_autograd/Wertinger_Calculus.md)以及[复数梯度计算](https://github.com/PaddlePaddle/community/blob/master/pfcc/paddle-code-reading/complex_autograd/complex_autograd.md)。
      2. 其次，需要对`python/paddle/tensor/ops.py`下的python接口进行更新。
      3. 最后，我们需要增加针对复数的相关测试，以便CI能对我们的提交进行检查。

    - 阅读 [zbt78](https://github.com/zbt78) 的 [周报](../../season%201/zbt78/) 和其提交的 pr : [59529](https://github.com/PaddlePaddle/Paddle/pull/59529), [60821](https://github.com/PaddlePaddle/Paddle/pull/60821)，了解相关任务的提交规范

    - 认领任务17 `Floor`算子，并进行调研

个人调研的`Floor`算子情况如下：

在维基百科中，Floor算子定义为实数域$\mathbb{R}$上的函数

$$
\left \lfloor{x}\right \rfloor  =\max\{m\in \mathbb{Z} \big| m<x\}
$$

对于点$x\in \mathbb{Z}$属于跳跃间断点，不可导；而对于$x\notin\mathbb{Z}$的点，其导数恒为0。在pytorch上进行了测试，floor算子下任意x的梯度均为0。

但是维基百科中没有涉及复数域$\mathbb{C}$的情况，同时我也没有看到比较官方的定义。我在[math.stackexchange](https://math.stackexchange.com/questions/2095674/floor-function-in-complex-plane/2095679#2095679) 看到两种方式，对于$x=ai+b$

一种是简单取虚数域和实数域上的floor

$$
\left \lfloor{ai+b}\right \rfloor=\left \lfloor{a}\right \rfloor i+\left \lfloor{b}\right \rfloor
$$

一种是令输出复数的模长等于输入复数的模长的floor

$$
\left \lfloor{ai+b}\right \rfloor=n(ai+b)
$$

其中$n\in\mathbb{R},n<1$，使得

$$
\vert \left \lfloor{ai+b} \right \rfloor \vert = \left \lfloor{\vert ai+b \vert} \right \rfloor 
$$

调研的`floor`函数对复数的支持情况如下：

 - ❌ `math`
 - ❌ `numpy`
 - ❌ `pytorch`
 - ✔️ `matlab`
 - ✔️ `mathematica` [文档](https://mathworld.wolfram.com/FloorFunction.html)


其中`matlab`和`mathematica`均使用第一种定义，因此考虑依从。

### **问题疑惑与解答**

   - 问题：关于复数域的floor有没有正式的定义？可以直接写吗？

     答：需要进一步调研讨论。

  - 问题：先前的会议是否有回放？

    答：没有，先前的会议仅对总体情况做了大致介绍，没有涉及专业知识。


### 未来双周计划

1. 继续完成Paddle本地编译任务。

2. 实现任务17 `Floor`算子对复数的支持。

