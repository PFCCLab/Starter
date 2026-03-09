### 姓名

韩芷依

### 本双周工作

#### FastDeploy 编译
- 状态：成功完成初次、二次编译，安装 whl 包并跑通单测。已发送证明邮件。
- 工作细节：
    - 初次编译：基于 [#6306](https://github.com/PaddlePaddle/FastDeploy/pull/6306) 在 V100 (SM70) 上顺利初次编译并生成 whl 包。过程中，解决了 cuda12.6 版本不兼容问题、三方库依赖下载失败等问题。
    - 二次编译：修改了 `transfer_output.cc`、`read_ids.py`、`kernel_traits.h`，并顺利成功二次编译。
    - 单测：调整了 `unittest` python 脚本并执行，成功验证 PR#6306 在 V100 上的兼容适配性。

#### 【GraphNet 热身打卡】计算图收集

- 状态：完成了基于 `torchaudio` 的 `wav2vec2_base` 模型的计算图抽取，已提交PR：[#669](https://github.com/PaddlePaddle/GraphNet/pull/669) 
- 工作细节
    - 按照约定的 5 项约束条件，编写了 `wav2vec_base_extract.py` 抽取脚本：
        - 输出接口规范：编写了 `Wav2Vec2Wrapper` 装饰类，仅保留特征向量输出；
        - 静态可分析：固定了输入的张量维度（ 1 * 16000 ），并配置了 `dynamic=False`；
        - 完成了 `Eager` 模式与抽取后模型的输出对比验证，确认了模型在 `eval` 模式下逻辑一致，且输出张量（ Shape/ Dtype ）符合预期。
    - 设置计算图保存路径并执行抽取脚本， 生成`graph_hash.txt`、`graph_net.json`、`input_meta.py`等计算图文件均收集入库
    - 使用 `graph_net.torch.validate` 工具完成自检，验证所提取的模型符合要求。
    - 收集整理了提取过程中遇到的各类问题，形成一份飞书笔记。

#### issue 管理

- 状态：针对 PR 所暴露的问题，优化了 issue 信息，参与 PR review 工作。
- 工作细节:
    - issue 优化：编写脚本提取错误链接，以表格形式在 comment 中列出；修改贡献表述，明确 Paddle 主库需要同步修改；删除了部分因渲染问题误判的失效链接。
    - PR review：聂师傅、Mo 师傅做了主要工作，我参与了辅助审查。
    - 沟通交流：帮助多个同学解决了修复过程中的问题，CI 通过率有所提升，加快了 PR review 的速度。

### 未来双周计划

- 跟进在 review 中的 PR，收尾遗留工作
- 继续参与【GraphNet 计算图收集】任务：抽取 `wav2vec2_base` 系列模型计算图，如 `wav2vec2_xlsr_2b` 、`wav2vec2_xlsr_1b` 等。由此进一步了解系列模型的特点，深入学习约束条件来由、学习 `graph_net.torch.validate` 与 `graph_net.torch.extract` 机制等。
- 学习 paddle 框架，多多参与到 Paddle 开源社区中来