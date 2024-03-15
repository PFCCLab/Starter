### 姓名

Atlantisming

### 开发中的快乐开源任务

暂无

### 本双周工作

1. **完成热身打卡三**

  - 使用AI Studio V100 32G 进行 Stable Diffusion 训练推理。

2. **了解 Grounding Dino 训练微调任务**

  - 完成 PaddleMix 和 mmdetection 环境配置，进行前向推理。
  - 阅读了论文及相关代码。

3. **问题疑惑与解答**
  
  - 问题 a：二次开发环境中使用添加系统路径方式`sys.path.append('extra_lib')`添加环境后仍无法找到相关库？

    答：目前没有解决这个问题，还是只能在打开开发环境后重新配置相关库。
    
  - 问题 b：与原仓库和 PaddleMix 不同，mmdetection 的 Grounding Dino 前向推理代码使用到了 `nltk` 进行分词处理，返回了单词的词性，并且在二次开发环境中下载时间较长？
    
    答：一种方法也是事先在本地下载相关包后上传到环境中，目前还未尝试。
    

### 未来双周计划

1. 继续阅读 Grounding Dino 论文及相关模型代码，了解 PaddleMix 其他训练微调逻辑。
2. Grounding Dino 的训练微调方式与开集训练方法不一致，是闭集方式的监督学习，尝试直接转写模型的损失函数。
