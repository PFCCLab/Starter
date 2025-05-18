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

### 周期内已完成任务/合入PR

#### Paddle Tensor 规范化二期
1. frobenius_norm对0-size tensor的支持，PR链接：https://github.com/PaddlePaddle/Paddle/pull/72570 

#### 【Docathon】补充缺失的中文 API 文档（Inplace 类）
2. No. 5、6、12，PR链接：https://github.com/PaddlePaddle/docs/pull/7294

3. No. 34、39，PR链接：https://github.com/PaddlePaddle/docs/pull/7139

4. No. 35，PR链接：https://github.com/PaddlePaddle/docs/pull/7129

#### 【Docathon】修复文档注解
5. No. 5、6、7，PR链接：https://github.com/PaddlePaddle/docs/pull/7138

6. No. 9、10，PR链接：https://github.com/PaddlePaddle/docs/pull/7222

#### 【Docathon】删除被弃用的API 
7. No. 18、19，PR链接：https://github.com/PaddlePaddle/docs/pull/7273

#### PaddleMIX 快乐开源活动 (2025 H1)
8. No.30，PR链接：https://github.com/PaddlePaddle/PaddleMIX/pull/1190

#### PaddleNLP 快乐开源活动 (2025 H1) 
9. 【No. 5 slm/applications/neural_search】，包含ranking与recall两个部分，共包含五个文件夹，4个模型与1个框架
        * In-Batch Negative，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10352
        * ernie_matching，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10399
        * fix cross encoder，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10398
        * milvus，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10397

10. 【PaddleNLP No.6】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10497

11. 【No. 9 slm/examples/machine_reading_comprehension】，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10445 解决用户提出的[bug report](https://github.com/PaddlePaddle/PaddleNLP/issues/10415) ，并且增加了一些运行环境相关的提示。 

12. 【PaddleNLP No.13 slm/examples/sentiment_analysis】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10454
   
13. 【PaddleNLP No.15 slm/examples/text_matching/ernie_matching】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10453

14. 【No. 18 slm/model_zoo/bert】PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10422

15. 【No. 19 slm/model_zoo/ernie-1.0】PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10426

16. 【PaddleNLP No.20】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10475 ，重新实现了支持paddle3.0.0的文本分类与NER两个任务的推理脚本，与无HF环境下的训练脚本。

17. 【PaddleNLP No.21 slm/model_zoo/ernie-3.0-tiny】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10480 ，重新实现了推理示例替代已经无法匹配paddle3.0.0的旧示例

18. 【PaddleNLP No.22】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10484

19. 【No. 26 slm/pipelines/pipelines/nodes/document】PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10394

20. 【No. 27 llm/server/server/server/engine/infer.py】PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10379

21. 【PaddleNLP No.28、34、35】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10456

22. 【PaddleNLP No.29-32】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10465 ，用'lite_train_lite_infer'模式对prepare/test_train_inference_python两条命令进行了验证，修复了bigru_crf固定python3.7运行的bug

#### 任务补充/bug修复
23. 对lexical_analysis文档中的推理命令进行更新；对ernie-vil2.0的数据生成脚本进行修复，并重新实现了适配paddle3.0.0的推理脚本。PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10500 ，Approved

24. 修复了在调用taskflow读取静态模型时PIR模型文件与id2label词典后缀都为.json时，taskflow错误将id2label.json读取为模型文件的错误。PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10487 ，Approved

25. 撰写PaddleNLP大模型预训练指南文档，并同步在aistudio构建项目，可以在线实验。PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10611 ，已提交

#### 其他工作
* 汇总PaddleNLP相关任务并与Mentor讨论后暂停No10-12、14、16-17任务并进行同步。


### 未来计划
1. 跟踪尚未完成合入的PR，根据mentor review意见进行修改；
2. 完成微调、对齐、量化的文档撰写。