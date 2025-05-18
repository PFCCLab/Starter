### 姓名

唐汉霖

### 开发中的快乐开源任务

PaddleNLP 快乐开源活动

Paddle Tensor 规范化二期

### 本双周工作

#### 合入PR
1. frobenius_norm对0-size tensor的支持，PR链接：https://github.com/PaddlePaddle/Paddle/pull/72570 

2. 【PaddleNLP No.20】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10475 ，重新实现了支持paddle3.0.0的文本分类与NER两个任务的推理脚本，与无HF环境下的训练脚本。

3. 【PaddleNLP No.22】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10484

4. 【PaddleNLP No.6】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10497

#### 已经Approved
5. 对lexical_analysis文档中的推理命令进行更新；对ernie-vil2.0的数据生成脚本进行修复，并重新实现了适配paddle3.0.0的推理脚本。PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10500

6. 修复了在调用taskflow读取静态模型时PIR模型文件与id2label词典后缀都为.json时，taskflow错误将id2label.json读取为模型文件的错误。PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10487

#### 已提交
7. 撰写PaddleNLP大模型预训练指南文档，并同步在aistudio构建项目，可以在线实验。PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10611


### 未来计划
1. 跟踪尚未完成合入的PR，根据mentor review意见进行修改；
2. 完成微调、对齐、量化的文档撰写。