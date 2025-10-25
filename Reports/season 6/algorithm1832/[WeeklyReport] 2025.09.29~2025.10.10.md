### 姓名

杨锃砚

### 开发中的快乐开源任务

- [PaddlePaddle PHI算子库CUDA Kernel规范化](https://github.com/PaddlePaddle/Paddle/issues/75226)

### 本双周工作

1. **[Docathon] 中文文档格式日常修复**

- saved_tensors_hooks_cn ([#7469](https://github.com/PaddlePaddle/docs/pull/7469), [#7504](https://github.com/PaddlePaddle/docs/pull/7504))

- Exponential_cn ([#7473](https://github.com/PaddlePaddle/docs/pull/7473))

2. **完成 Paddle 本地编译**

- 利用aistudio完成Paddle本地编译
- 每次修改Paddle仓库后，执行本地编译确定不存在问题

3. **Stable-Diffusion 训练推理**

- 利用aistudio完成PaddleMIX中stable-diffusion模型的训练和测试

4. **PaddlePaddle PHI算子库CUDA Kernel规范化**

- box_clip_kernel.cu ([#75592](https://github.com/PaddlePaddle/Paddle/pull/75592), [#2021](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2021))
- c_concat_kernel.cu ([#75648](https://github.com/PaddlePaddle/Paddle/pull/75648))
- c_embedding_grad_kernel.cu ([#2036](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2036))
- c_scatter_kernel.cu ([#75653](https://github.com/PaddlePaddle/Paddle/pull/75653))

- 目前正在等待[#2021](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2021)中提问的回复

### 未来双周计划

- 继续执行**PaddlePaddle PHI算子库CUDA Kernel规范化**任务
  - 收到[#2021](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2021)的回复后继续完成c_concat_kernel.cu和c_scatter_kernel.cu在PaddleCustomDevice的修改
  - 可能还会再认领几个任务

### 其它

- 在aistudio上进行Paddle编译，使用相同的参数，编译速度却不一样，而且有时正常编译，有时会发生子进程被kill的情况（疑似内存不足，但通过top查看内存又足够）。推测为aistudio分配的虚拟资源的关系。
- Paddle文档存在一些死链，点进去会404。甚至在编译Paddle([issue#45347](https://github.com/PaddlePaddle/Paddle/issues/45347))中出现的链接也是404。希望之后能够参与修复。
- PaddleCustomDevice仓库CI报错，是因为Paddle仓库中`FusedLayerNormKernel`的namespace不对，这个错已经被修好了（[#75589](https://github.com/PaddlePaddle/Paddle/pull/75589)），但是PaddleCustomDevice仓库中的子模块没有更新。



非常感谢@Echo-Nie, @YqGe585老师的指导！