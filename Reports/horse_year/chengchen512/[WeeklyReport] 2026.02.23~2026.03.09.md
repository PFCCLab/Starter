#### 姓名
陈铖

#### 开发中的快乐开源任务
* 【快乐开源】PaddlePaddle 文档链接修复任务
* 【GraphNet 热身打卡】计算图收集任务

#### 本双周工作
1.  **FastDeploy编译**
    *  在 PR #6306（commit: 48adbc40fc29d0cd660311d141eff0ca48f037d2）分支下完成了环境的初次编译与二次编译测试。
    *  对 `kernel_traits.h`、`transfer_output.cc` 和 `read_ids.py` 等算子和脚本文件进行了修改并重新成功编译。
    *  成功安装了生成的 whl 包，并编写 Python 脚本验证了当前 GPU 平台架构的 SM Version 正确识别为 70（即 V100 显卡）。

2.  **PaddlePaddle 文档链接修复**
    *  参与了 #[7735](https://github.com/PaddlePaddle/docs/issues/7735) 文档修复任务，成功提交并合入了两个修复动态 RNN 设计文档失效链接的 PR。
    *  提交并合入 PR #[7789](https://github.com/PaddlePaddle/docs/pull/7789)（修复 `docs/design/dynamic_rnn/rnn.md`）：将原指向 FluidDoc 的外链图片替换为相对路径引用（如 `../../images/rnn.png`），解决了文档构建依赖网络及非开发分支内容不一致的问题。
    *  提交并合入 PR #[7819](https://github.com/PaddlePaddle/docs/pull/7819)（修复 `docs/design/dynamic_rnn/rnn_design.md`）：将文中失效的 TensorFlow (r0.12版本) 和 MXNet (mxnet.io域名) 的 Bucketing API 链接，更新为当前可访问的官方正确链接。

3.  **【GraphNet 热身打卡】计算图收集**
    *  提交并合入 PR #[664](https://github.com/PaddlePaddle/GraphNet/pull/664)，为模型 `perplexity-ai/pplx-embed-v1-0.6b` 添加了基于 PyTorch 框架的计算图示例。
    *  提供了用于复现的提取脚本，并采用静态抽取模式（Static extraction mode）以提升验证的稳定性。

#### 未来双周计划
1. 持续关注 PaddlePaddle 开源社区，跟进其他开发任务。
2. 参与 GraphNet 更多新模型的计算图收集与验证工作。