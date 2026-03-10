### 姓名

ClaireJunc

### 本双周工作

1. **参与 GraphNet 热身打卡活动**
   - 响应 [GraphNet 热身打卡计算图收集](https://github.com/PaddlePaddle/GraphNet/issues/370) 活动号召，完成模型计算图的抽取、验证和提交全流程
   - 选择了 torchvision 中尚未收集的 `swin_t`（Swin Transformer Tiny）模型作为目标
   - 配置开发环境，安装 PyTorch、torchvision 等依赖

2. **编写抽取脚本并提取计算图**
   - 参考已有的 `vision_model_test.py` 等脚本，编写了 `graph_net/test/swin_t_extract_test.py` 抽取脚本
   - 使用 `torchvision.models.get_model` 加载模型，通过 `graph_net.torch.extract` 装饰器成功抽取计算图
   - 使用标准 ImageNet 输入 `(1, 3, 224, 224)`，采用静态形状模式（dynamic=False）

3. **验证并提交 PR**
   - 使用 `graph_net.torch.validate` 验证计算图通过所有 Dataset Construction Constraints
   - 将样本整理至 `samples/torchvision/swin_t/` 目录，包含 `model.py`、`weight_meta.py`、`graph_net.json`、`graph_hash.txt` 等完整文件
   - 已提交 PR：[New Sample: Add "swin_t" Model Computational Graph](https://github.com/PaddlePaddle/GraphNet/pull/653)

### 未来双周计划

1. 跟进 PR #653 的 CI 检查及 Review 反馈，及时修正问题
2. 继续参与 GraphNet 计算图收集，尝试提取更多未覆盖的模型（如 swin_s、mc3_18 等）
3. 深入学习 GraphNet 的 extractor 和 validate 机制，探索 dynamic shape 模式的支持
