### 姓名

叶佩姿

### 本双周工作

#### 1. PaddlePaddle API 兼容性增强任务

本双周认领了 No.122 任务，目标是增强 `paddle.neg` 与 PyTorch 的 `torch.neg` 兼容性，已提交 PR：[https://github.com/PaddlePaddle/Paddle/pull/78216。由于首次接触该框架，前期花费较多时间阅读源码与调研实现方案，PR](https://github.com/PaddlePaddle/Paddle/pull/78216。由于首次接触该框架，前期花费较多时间阅读源码与确定实现方案，PR) 目前尚未 merge。主要修改内容：增加了参数别名（支持 `input` 作为 `x` 的别名）、新增 `out` 参数以支持就地写入、更新了 docstring 并补充了兼容性测试（新增 `TestNeg`）。
