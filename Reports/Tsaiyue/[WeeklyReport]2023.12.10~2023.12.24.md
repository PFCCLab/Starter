### 姓名

Tsaiyue

### 开发中的快乐开源任务

Kandinsky2.2 训练支持

### 本双周工作

1. 跑通diffusers下KandinskyV22 example的微调，获取部分对齐损失数据，包含prior、decoder下w or w / o LoRA;

2. 跑通PaddleMIX下text2image下的example(其文件结构与KandinskyV22类似)微调和推理代码;

3. 学习PaConvert的使用，将其对diffusers中的KandinskyV22示例进行转换;

4. **问题疑惑与解答**
   
   - 问题 a：as无法下载hf上微调数据.
     
     答：本地下载，外部导入as.

### 未来双周计划

1. 在PaConvert转换基础上修改，跑通基于Paddle的example;

2. 获取基于Paddle的微调损失数据，包含prior、decoder下w or w / o LoRA.
