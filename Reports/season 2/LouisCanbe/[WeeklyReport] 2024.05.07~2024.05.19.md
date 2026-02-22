### 姓名

吴小龙（LouisCanBe）

### 开发中的快乐开源任务

合入一个PR，[[Docathon]Add a new API documentation (paddle.renorm#6625) ][#6625]
  
### 本双周工作

1. **完善新增加的api文档的（paddle.renorm）** 已合入[#6625]
    - 根据review，完善补全中文api文档，来源:[官网貌似没有paddle.renorm API的相关文档#6508](https://github.com/PaddlePaddle/docs/issues/6508)

2. **完成打卡任务**2，3

- **ⅱ. 完成 Paddle 本地编译**✔️
  - 主要在于配置好环境，使用编译命令设置好参数，开启单元测试，注意python版本等
  - 参考链接：
    - [【热身打卡】开发框架，从编译 paddle 开始 · Issue #45347 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/issues/45347)
    - [常见IDE利用Docker完美查看Paddle源码跳转](https://aistudio.baidu.com/aistudio/projectdetail/5314922)

- **ⅲ. Stable-Diffusion 训练推理**✔️
  - 框架版本，硬件版本，CUDA版本，依赖版本适配问题比较难调整:
    - huggingface_hub 版本适配问题，0.23.0 版本不支持，需要降级到0.22.2

  - error_fix_try：
    - set _default_dtype only supports [float16, float32, float64, bfloat16], but received paddle.float32
    - ![set _default_dtype only supports [float16, float32, float64, bfloat16], but received paddle.float32](images/error_paddle.float32.png)
  - 参考链接：
    - [【PaddleMIX 热身打卡】跑通 Stable-Diffusion 训练推理-Github](https://github.com/PaddlePaddle/PaddleMIX/issues/273)
    - [【PaddleMIX 热身打卡】跑通 Stable-Diffusion 训练推理 - 飞桨AI Studio星河社区](https://aistudio.baidu.com/projectdetail/7649127?channelType=0&channel=0)
  
### 未来双周计划

1. **继续尝试给Tensor API文档增加图例 的任务**
  - [【Docathon】为 Tensor API 文档增加图例 · Issue #6614 · PaddlePaddle/docs](https://github.com/PaddlePaddle/docs/issues/6614)
     1. 阅读api文档，理解方法意义
     2. 使用工具表示api作用
     3. 参考GPT等使用matpliotlib画出图例

[#6625]:https://github.com/PaddlePaddle/docs/pull/6625