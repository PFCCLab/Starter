### 姓名

杨锃砚

### 开发中的快乐开源任务

- [PaddlePaddle PHI算子库CUDA Kernel规范化](https://github.com/PaddlePaddle/Paddle/issues/75226)

### 本双周工作

1. **中文文档修复**

- 修复rnnt_loss_cn的渲染问题（[#7568](https://github.com/PaddlePaddle/docs/pull/7568)）
- 修复中文文档内PDF文件链接404问题（[#7555](https://github.com/PaddlePaddle/docs/pull/7555), [#7557](https://github.com/PaddlePaddle/docs/pull/7557), [#7560](https://github.com/PaddlePaddle/docs/pull/7560)）


2. **PaddlePaddle PHI算子库CUDA Kernel规范化**

- box_clip_kernel.cu ([#2021](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2021))
- c_concat_kernel.cu ([#2052](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2052))
- c_embedding_grad_kernel.cu ([#2036](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2036))
- c_scatter_kernel.cu ([#2059](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2059))
- gru_kernel.cu ([#75845](https://github.com/PaddlePaddle/Paddle/pull/75845))
- index_add_grad_kernel.cu ([#2071](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2071))
- interpolate_grad_kernel.cu ([#75974](https://github.com/PaddlePaddle/Paddle/pull/75974))
- 列表内容包含：本周进行的工作，非本周进行但未合并的工作。未合并工作不定时trigger re-run。


### 未来双周计划

- 继续执行**PaddlePaddle PHI算子库CUDA Kernel规范化**任务
- 或许会尝试一下[#74773](https://github.com/PaddlePaddle/Paddle/issues/74773)的任务

### 其它

- Paddle仓库的CI疑似有点问题，下面这些CI都没有运行结果，直接中途退出，也没法通过exit code排查原因
  - CI-Build / Auto-Parallel / Parallel test (pull_request)
  - CI-Build / Model-Benchmark / Benchmark test (pull_request)
  - CI-Build / Static-Check / Test (pull_request)
- docs中`Paddle.static.Program`文档的渲染问题还在调查中



非常感谢@Echo-Nie, @YqGe585老师的指导！

