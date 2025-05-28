### 姓名

朱萌萌

### 开发中的快乐开源任务

PaddleMIX 快乐开源活动 (2025 H1)

### 本双周工作

1. **任务 - PaddleMIX 快乐开源活动**

   - 提交了 mar 框架迁移 PR，待审阅

### 致谢
感谢老师的帮助与指导，感谢助教老师、同学们的热心帮助，感谢开源社区的优秀文档，收获颇多，很有意义的经历。

### 已完成的PR链接
1. 已完成
- https://github.com/PaddlePaddle/docs/pull/7155

2. 审阅中
- https://github.com/PaddlePaddle/PaddleMIX/pull/1280


### 开发中遇到的 API 建议
- Paddle 与 Torch 的张量随机生成 API，即使定义同一个 seed，产生的结果却不同，但在我参考的许多文档中，似乎并没有明确表明这一点，只是提到了要设置成相同的 seed，或者说在什么情况下两者会保持一致？
- Paddle.scatter API 并没有自动填充维度的功能，灵活度低于 Torch.scatter，本人依靠大语言模型，暂时实现了基础的广播功能，但由于没有仔细核查代码，可能并不具有鲁棒性。参考 Torch.scatter_() 完全迁移实现感觉不会困难，希望能在下个版本有所更新。
