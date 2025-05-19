### 姓名

唐汉霖

### 开发中的快乐开源任务

PaddleNLP 快乐开源活动

Paddle Tensor 规范化二期

### 本双周工作

#### Paddle Tensor 规范化二期

1. 增加frobenius_norm对0-size tensor的支持，PR链接：https://github.com/PaddlePaddle/Paddle/pull/72570

#### 【Docathon】删除被弃用的API
    
2. [Delete Deprecated API Doc No.18、19]，PR链接：https://github.com/PaddlePaddle/docs/pull/7273 ，已合入

#### 【Docathon】补充缺失的中文 API 文档（Inplace 类）
3. [Add Inplace CN Doc No.5、6、12] PR链接：https://github.com/PaddlePaddle/docs/pull/7294 ，已合入

#### PaddleNLP 快乐开源活动
**Paddle 高扩展中间表示PIR适配（已合入PR）**

4. 上周期提交，本周期合入的PR：
    * [【No. 9】](https://github.com/PaddlePaddle/PaddleNLP/pull/10445)
    * [【No. 18】](https://github.com/PaddlePaddle/PaddleNLP/pull/10422)

5. 【PaddleNLP No.13 slm/examples/sentiment_analysis	】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10454 ，已合入
   
6. 【PaddleNLP No.15 slm/examples/text_matching/ernie_matching】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10453 ，已合入

7. 【PaddleNLP No.21 slm/model_zoo/ernie-3.0-tiny】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10480 ，已合入，重新实现了推理示例替代已经无法匹配paddle3.0.0的旧示例

8. 【PaddleNLP No.28、34、35】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10456 ，已合入

9. 【PaddleNLP No.29-32】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10465 ，已合入，用'lite_train_lite_infer'模式对prepare/test_train_inference_python两条命令进行了验证，修复了bigru_crf固定python3.7运行的bug

**Paddle 高扩展中间表示PIR适配（已提交PR）**

10. 【PaddleNLP No.20】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10475 ，重新实现了支持paddle3.0.0的文本分类与NER两个任务的推理脚本，与无HF环境下的训练脚本。

11. 【PaddleNLP No.22】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10484

12. 【PaddleNLP No.6】PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10497

**任务补充**

13. 对lexical_analysis文档中的推理命令进行更新；对ernie-vil2.0的数据生成脚本进行修复，并重新实现了适配paddle3.0.0的推理脚本。PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10500

#### PaddleNLP bug修复
14. 修复了在调用taskflow读取静态模型时PIR模型文件与id2label词典后缀都为.json时，taskflow错误将id2label.json读取为模型文件的错误。PR链接：https://github.com/PaddlePaddle/PaddleNLP/pull/10487

#### 其他
15. 汇总相关任务并与Mentor讨论后暂停No10-12、14、16-17任务并进行同步。

3. **问题疑惑与解答**

   - 暂无


### 未来双周计划

1. 跟踪尚未完成合入的PR，根据mentor review意见进行修改；
2. 报名剩余的PaddleNLP任务，提交PR；
3. 了解其他快乐开源任务，开展针对性学习。