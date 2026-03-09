### 姓名

刘京宗

### 本双周工作

在过去的两周中，我主要参与了 PaddlePaddle **API 兼容性增强（启航计划）**的相关开发工作，重点针对 `paddle.poisson` 接口进行了全栈式的优化与适配，涵盖了核心框架实现、文档更新及转换工具支持：

1. **Paddle 核心框架功能增强 ([Paddle/pull/77715](https://github.com/PaddlePaddle/Paddle/pull/77715))**
* **任务内容**：负责 `paddle.poisson` 算子的 API 兼容性改造。
* **具体修改**：通过 C++ 下沉或装饰器机制，为 `paddle.poisson` 接口增加了对参数别名（如 `input` 等）的支持。这一改动旨在对齐主流深度学习框架（如 PyTorch）的使用习惯，减少用户在模型迁移过程中的代码修改量，提升了框架的易用性和兼容性。


2. **官方文档同步更新 ([docs/pull/7831](https://github.com/PaddlePaddle/docs/pull/7831))**
* **任务内容**：针对 `paddle.poisson` 接口的功能变动同步更新中英文文档。
* **具体修改**：在文档中明确了新增参数的支持情况，完善了 API 的参数列表描述及代码示例，确保开发者能够清晰地了解如何使用优化后的接口。


3. **代码转换工具 PaConvert 适配 ([PaConvert/pull/841](https://github.com/PaddlePaddle/PaConvert/pull/841))**
* **任务内容**：在代码自动化转换工具中新增对 `poisson` 相关 API 的转换逻辑。
* **具体修改**：建立了 `torch.poisson` 到 `paddle.poisson` 的映射规则。通过该 PR，用户在使用 PaConvert 工具迁移 PyTorch 模型代码时，能够自动、准确地完成该算子的转换，进一步完善了迁移工具链的覆盖范围。



### 未来双周计划

继续为 paddle 开源社区做出贡献