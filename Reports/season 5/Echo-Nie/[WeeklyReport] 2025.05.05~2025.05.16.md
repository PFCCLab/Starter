### 姓名

聂宇旋



### 本双周工作

1. **文档类**
   
   - 【删除 + 修改】原 fluid 部分的 activations：按照 Paddle 1.8 与 Paddle 2.0 API 映射表的要求，对激活函数相关文档进行了全面修复和更新，完成了过时 API 的替换、移除，部分 API 命名的优化调整。PR已合入：https://github.com/PaddlePaddle/docs/pull/7297
   - 针对activations内容，发现其文档并没有与源码对齐，于是参照源码进行补充与测试（Inplace的激活函数未加入），发现develop分支下的所有激活函数都可以正常使用，于是有了这个PR，https://github.com/PaddlePaddle/docs/pull/7305
   - 做任务顺便看到的链接失效问题：https://github.com/PaddlePaddle/docs/pull/7303
   - 针对pad的 [Issue #7299](https://github.com/PaddlePaddle/docs/issues/7299) 中提出的奇偶数问题对函数进行测试，发现奇偶数的填充规则不一样（奇数会自动填充为偶数，但是可能会有一些潜在问题，所以不建议奇数），提出PR：https://github.com/PaddlePaddle/docs/pull/7300
   
   
   
2. **PaddleScience** 

   - 完成打卡，在尝试做Science的模型导出... 
   
   
   
3. **Paddle2Torch API**

   - 正在尝试做Torch API 转换功能开发的任务中的 `reshape` ，还没PR...

   

4. **PaddleNLP** 

   - 扩充[预训练文档](https://github.com/PaddlePaddle/PaddleNLP/tree/develop/llm#1-预训练)，PR：https://github.com/PaddlePaddle/PaddleNLP/pull/10506 （已合入）

   

### 致谢

感谢各位老师的指导！



### 本期合入的所有PR

#### PaddleSpeech

https://github.com/PaddlePaddle/PaddleSpeech/pull/4004

https://github.com/PaddlePaddle/PaddleSpeech/pull/4013

https://github.com/PaddlePaddle/PaddleSpeech/pull/4047

https://github.com/PaddlePaddle/PaddleSpeech/pull/4050

https://github.com/PaddlePaddle/PaddleSpeech/pull/4051

https://github.com/PaddlePaddle/PaddleSpeech/pull/4037

https://github.com/PaddlePaddle/PaddleSpeech/pull/4038

https://github.com/PaddlePaddle/PaddleSpeech/pull/4049

https://github.com/PaddlePaddle/PaddleSpeech/pull/4044

https://github.com/PaddlePaddle/PaddleSpeech/pull/4043

https://github.com/PaddlePaddle/PaddleSpeech/pull/4042

https://github.com/PaddlePaddle/PaddleSpeech/pull/4057



#### PaddleDocs

https://github.com/PaddlePaddle/docs/pull/7108

https://github.com/PaddlePaddle/docs/pull/7132

https://github.com/PaddlePaddle/docs/pull/7164

https://github.com/PaddlePaddle/docs/pull/7178

https://github.com/PaddlePaddle/docs/pull/7177

https://github.com/PaddlePaddle/docs/pull/7213

https://github.com/PaddlePaddle/docs/pull/7178

https://github.com/PaddlePaddle/docs/pull/7177

https://github.com/PaddlePaddle/docs/pull/7153

https://github.com/PaddlePaddle/docs/pull/7235

https://github.com/PaddlePaddle/docs/pull/7264

https://github.com/PaddlePaddle/docs/pull/7268

https://github.com/PaddlePaddle/docs/pull/7271

https://github.com/PaddlePaddle/docs/pull/7283

https://github.com/PaddlePaddle/docs/pull/7284

https://github.com/PaddlePaddle/docs/pull/7227

https://github.com/PaddlePaddle/docs/pull/7228

https://github.com/PaddlePaddle/docs/pull/7278

https://github.com/PaddlePaddle/docs/pull/7097

https://github.com/PaddlePaddle/docs/pull/7135

https://github.com/PaddlePaddle/docs/pull/7182

https://github.com/PaddlePaddle/docs/pull/7303

https://github.com/PaddlePaddle/docs/pull/7305

https://github.com/PaddlePaddle/docs/pull/7297



#### PaddleNLP

https://github.com/PaddlePaddle/PaddleNLP/pull/10470

https://github.com/PaddlePaddle/PaddleNLP/pull/10469

https://github.com/PaddlePaddle/PaddleNLP/pull/10481

https://github.com/PaddlePaddle/PaddleNLP/pull/10466

https://github.com/PaddlePaddle/PaddleNLP/pull/10482

https://github.com/PaddlePaddle/PaddleNLP/pull/10460

https://github.com/PaddlePaddle/PaddleNLP/pull/10505

https://github.com/PaddlePaddle/PaddleNLP/pull/10506 



#### 提出了一些简单的Issue

[Paddle的Overview中稀疏API渲染 · Issue #7302 · PaddlePaddle/docs](https://github.com/PaddlePaddle/docs/issues/7302)

[pretrain.rst 中的 llm_train.rst 链接失效 · Issue #10504 · PaddlePaddle/PaddleNLP](https://github.com/PaddlePaddle/PaddleNLP/issues/10504)

[【Docathon】删除被弃用的API · Issue #7238 · PaddlePaddle/docs](https://github.com/PaddlePaddle/docs/issues/7238)

[Oveview的中关于Inplace对应原API的链接问题 · Issue #7279 · PaddlePaddle/docs](https://github.com/PaddlePaddle/docs/issues/7279)

[Exception API 失效文档链接 - errors · Issue #72399 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/issues/72399)

[Profiler 引用冗余？ · Issue #7253 · PaddlePaddle/docs](https://github.com/PaddlePaddle/docs/issues/7253)

[Not Found module regex · Issue #1131 · PaddlePaddle/PaddleMIX](https://github.com/PaddlePaddle/PaddleMIX/issues/1131)

跟踪的一个 `pad` 函数的文档issue： [Issue #7299](https://github.com/PaddlePaddle/docs/issues/7299) 与 [PR for pad](https://github.com/PaddlePaddle/docs/pull/7300) 

一处代码冗余的PR：[del rgex PaddleMIX](https://github.com/PaddlePaddle/PaddleMIX/pull/1184)



