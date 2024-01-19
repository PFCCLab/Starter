### 姓名

徐梓铭 (Atlantisming)

### 开发中的快乐开源任务

暂无

### 本双周工作

1. **实现 Grounding Dino 训练微调**

  - 在本地重新配置了 mmdetection 的 Grounding Dino 环境。
  - 验证了 PaddleMix 和 mmdetection 前向推理。
  - 配置了 cat 小数据集，得到了微调的损失值。

2. **正在进行 Grounding Dino 反向对齐**

  - 使用 PaConvert 转换了匈牙利匹配函数和损失函数。
  - 学习 PPNLP 中 trainer 逻辑。

3. **问题疑惑与解答**
  
  - 问题：无法连接到 nltk_data 下载？

    答：可能需要配置浏览器访问权限，或者直接在 http://www.nltk.org/nltk_data/ 下载，并根据提示放置相应的数据。

### 未来双周计划

1. 继续阅读 Grounding Dino 论文及相关模型代码，了解 PaddleMix Trainer 训练微调逻辑。
2. 完成反向对齐。
