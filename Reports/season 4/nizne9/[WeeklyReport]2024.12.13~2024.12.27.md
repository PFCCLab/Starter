### 姓名

钟至佳(@nizne9)

### 开发中的快乐开源任务

1. CINN编译器后端Pass改造：`optim/transform_gpu_forloop.cc`
2. PaddleMix 快乐开源活动中的 sam2 推理
3. 根据 review 意见修改 `paddle.where`，`paddle.linalg.vector_norm` 的 PR

### 本双周工作

1. **✏️ Typo 清理计划**
   * 修复了十余个 typos [#70482](https://github.com/PaddlePaddle/Paddle/pull/70482)

2. **Paddle Tensor 规范化项目-第2期**
   * 为 `paddle.unstack` 支持 0-size Tensor [#70342](https://github.com/PaddlePaddle/Paddle/pull/70342)
   * `paddle.where` 鲁棒性增强 [#70408](https://github.com/PaddlePaddle/Paddle/pull/70408)
   * 更改 `paddle.atan2` 的广播方案，从 Kernel 移动到 Python 进行，减少对符号推导的影响 [#70468](https://github.com/PaddlePaddle/Paddle/pull/70468)
   * `paddle.linalg.vector_norm` 鲁棒性增强 [#70499](https://github.com/PaddlePaddle/Paddle/pull/70499)

3. **问题疑惑与解答**

   * `paddle.broadcast_to` 无法正确处理 GPU 下标量广播到 0-size 的情况，会出现段错误

      答：与 @fxy1699 进行排查后，修改 ExpandKernel 后解决 [#70468](https://github.com/PaddlePaddle/Paddle/pull/70468)

### 未来双周计划

1. 合入`paddle.where`，`paddle.linalg.vector_norm` 两个 PR
2. 阅读 CINN 的文档，完成第一版的 `optim/transform_gpu_forloop.cc`
3. 完成 sam2 模型的对齐，并着手进行 appflow 的接入
