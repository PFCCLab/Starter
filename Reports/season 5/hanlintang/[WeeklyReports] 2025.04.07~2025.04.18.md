### 姓名

唐汉霖

### 开发中的快乐开源任务

PaddleNLP 快乐开源活动

PaddleMIX 快乐开源活动

### 本双周工作

1. **PaddleMIX 快乐开源活动**

   - 完成【任务No.30】 **收集和整理新应用** 新增12个应用，并且整理了分类，加入了文本生成类的应用（PR 链接：https://github.com/PaddlePaddle/docs/pull/7129） ，已合入

2. **PaddleNLP 快乐开源活动** Paddle 高扩展中间表示PIR适配

   - 修改源代码，加入PIR适配后缀
     1. 【No. 26 slm/pipelines/pipelines/nodes/document】PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10394 ，已合入
     2. 【No. 27 llm/server/server/server/engine/infer.py】PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10379 ，已合入
   - 进行pipeline的完整验证，并针对paddle/paddleNLP版本变更debug代码与补全文档，同时适配PIR
     1. 【No. 5 slm/applications/neural_search】，包含ranking与recall两个部分，共包含五个文件夹，4个模型与1个框架
        * In-Batch Negative，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10352 ，已合入
        * ernie_matching，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10399 ，已合入
        * fix cross encoder，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10398 ，已合入
        * milvus，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10397 ，已合入
        * simcse，PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10396 ，完成修改，已与mentor沟通触发bug
     2. 【No. 9 slm/examples/machine_reading_comprehension】，遇到用户提出的[bug report](https://github.com/PaddlePaddle/PaddleNLP/issues/10415) 后进行了修复，并且增加了一些运行环境相关的提示。 PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10445 ，已提交
   - 由于paddle 3.0.0与paddle项目内部署工具（如：等）不再匹配，需要重新实现基于paddle.inference的推理，同时适配PIR
     1. 【No. 19 slm/model_zoo/ernie-1.0】PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10426 ，已合入
     2. 【No. 18 slm/model_zoo/bert】PR 链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10422 ，等待验证流水线
   - 【No. 19 slm/model_zoo/ernie-1.0】暂时跳过需要后续再处理，相关情况提交了[issue](https://github.com/PaddlePaddle/PaddleNLP/issues/10439)

3. **问题疑惑与解答**

   - 暂无


### 未来双周计划

1. 完成报名的PaddleNLP任务，提交PR；
2. 跟踪尚未完成合入的PR，根据mentor review意见进行修改；
3. 了解其他快乐开源任务，开展针对性学习。