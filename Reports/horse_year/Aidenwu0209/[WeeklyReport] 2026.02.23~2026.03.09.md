# [WeeklyReport] 2026.02.23~2026.03.09

### 姓名

Aidenwu0209

### 本双周工作

1. 在 `PaddlePaddle/Paddle#76301` 中完成 `No.154`、`No.155`、`No.186`、`No.187`、`No.188` 五项 API 兼容性任务，分别为 `binary_cross_entropy`、`binary_cross_entropy_with_logits`、`mse_loss`、`multi_margin_loss`、`nll_loss` 补齐与 PyTorch 对齐的参数别名支持，如 `target -> label`、`input -> logit`，其中 `No.155`、`No.186`、`No.187`、`No.188` 已获得 reviewer approval，`No.187` 在更新后仍保持 approval，`No.154` 已根据 reviewer 意见继续修改并提交最新版本，正在持续跟进。
2. 完成 `No.185` 和 `No.190` 两项兼容性改动，在 `PaddlePaddle/Paddle#77923` 和 `PaddlePaddle/Paddle#77920` 中分别为 `mish` 和 `pixel_unshuffle` 增加 `input` 参数别名支持，相关改动已合入主仓。
3. 完成 `No.191`、`No.214`、`No.218` 三项兼容性任务，分别为 `poisson_nll_loss`、`rot90`、`select_scatter` 补齐参数别名支持，并同步提交对应的 `PaConvert` 和 `docs` PR，完善迁移规则与文档说明，其中 `No.191`、`No.214`、`No.218` 均已获得 reviewer approval，`No.218` 已在更新后重新获得 reviewer approval。
4. 完成 `PaddlePaddle/PaddleOCR#17690`，为 PaddleOCR 从零开发并接入 `paddleocr-text-recognition` 和 `paddleocr-doc-parsing` 两个 official skills，完成技能脚本封装、API 调用链路接入、配置向导、smoke test、使用说明与示例补充，并通过 `PaddlePaddle/PaddleOCR#17766` 完善 `Client-Platform` header；同时持续推进 `PaddlePaddle/PaddleOCR#17771` 和 `PaddlePaddle/PaddleOCR#17778`，优化 skills 的 README onboarding 流程、安装配置与冒烟测试说明、聊天示例，以及默认将原始 JSON 结果保存到 `tmp/.../result.json` 的 workflow。

### 详细周报链接：

https://github.com/PFCCLab/Starter/pull/861
