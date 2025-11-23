### 姓名

杨锃砚

### 开发中的快乐开源任务

- [PaddlePaddle PHI算子库CUDA Kernel规范化](https://github.com/PaddlePaddle/Paddle/issues/75226)

### 本双周工作

1. **中文文档修复**

- 生成文档支持函数的`posonlyargs`（[#7578](https://github.com/PaddlePaddle/docs/pull/7578)）


2. **PaddlePaddle PHI算子库CUDA Kernel规范化**

- 【No.35】c_scatter_kernel.cu ([#2059](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2059))
- 【No.60】gru_kernel.cu ([#2126](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2126))
- 【No.62】interpolate_grad_kernel.cu ([#2127](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2127))
- 【No.63】interpolate_grad_kernel.cu ([#76261](https://github.com/PaddlePaddle/Paddle/pull/76261))
- 【No.64】kldiv_loss_grad_kernel.cu ([#2117](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2117))
- 列表内容包含：本周进行的工作，非本周进行但未合并的工作。未合并工作不定时合develop。


### 未来双周计划

- 继续执行**PaddlePaddle PHI算子库CUDA Kernel规范化**任务
- 【计划已延误】或许会尝试一下[#74773](https://github.com/PaddlePaddle/Paddle/issues/74773)的任务

### 其它

- 期中临近，一些课程开始布置作业了，这两周因为做作业花费了一些时间，导致双周计划发生延误
- 做课程作业用到了Baidu AiStudio的Notebook项目，运行的时候发现notebook单元格跑完了内存没释放，最后内存直接上95%了，重启内核可以解决，不过还是想问一下是怎么回事（单元格内容为`%run ./mnist.py`，mnist.py是我自己创建的）



非常感谢 @SigureMo, @YqGe585, @Echo-Nie, @sunzhongkai588, @luotao1 老师的指导！

