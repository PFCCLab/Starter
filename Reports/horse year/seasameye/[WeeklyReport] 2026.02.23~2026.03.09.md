### 姓名

叶佩姿

### 本双周工作

#### 1. PaddlePaddle API 兼容性增强任务

本双周认领了 No.122 任务，目标是增强 `paddle.neg` 与 PyTorch 的 `torch.neg` 兼容性。

已提交 PR：PaddlePaddle/Paddle#78216

由于首次接触该框架，前期花费较多时间阅读文档与确立实现方案，因此 PR 目前尚未 merge。

主要修改内容：为 `neg` API 增加参数别名支持（允许 `input` 作为 `x` 的别名），新增 `out` 参数以支持结果写入预分配 Tensor，同时更新了 docstring 并补充了兼容性测试（新增 `TestNeg`）。
