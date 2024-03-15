### 姓名

Tsaiyue

### 开发中的快乐开源任务

Kandinsky2.2 训练支持

### 本双周工作

1. **学习kandinskyV22在diffusers下的具体实现**
   
   - 模型结构基于Dalle2，微调部分为decoder中以image embedding为条件学习到VQModel中间latent的扩散模型，以及prior中以text embedding为条件到image embedding的扩散模型。整个流程中与CLIP相关的model以及VQModel均来自预训练好的权重;
   
   - 推断用到的pipiline主要为KandinskyV22Combinepipeline，来源于AutoText2ImagePipeline，其更具hf上model_index.json中的_class_属性选择对应的pipeline;
   
   - LoRA为一种PEFT技术，在decoder和prior的应用中针对attention layer构造lora_layers.

2. **对diffusers中基于Pytorch的KandinskyV22的example进行跑通**

3. **问题疑惑与解答**
   
   - 无

### 未来双周计划

1. 了解kandinskyV22所用模块在paddleMIX中的支持情况；
2. 先完成针对decoder的训练微调对齐。
