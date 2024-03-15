### 姓名

NKNaN

### 开发中的快乐开源任务

AudioLDM2模型复现前向推理

### 本双周工作

1. **学习paddle底层kernel的设计方法**

   - Paddle API：详细阅读了 paddle 贡献指南中新增 API 时开发 c++ 算子与 python 端 API 的说明。初步学习了 cuda 算子的写法。
   
   - 参考其他同种类关于分布采样的 c++ 算子，以及 binomial 的 torch 实现方法，提交了新增 binomial 算子的 pr ：<https://github.com/PaddlePaddle/Paddle/pull/59690>


2. **大模型快乐开源任务**

   - 阅读 [AudioLDM2 代码](https://github.com/haoheliu/AudioLDM2)，梳理了部分代码的逻辑，并尝试将已经梳理的代码转化为 Paddle 框架，本双周梳理部分主要包括：
     1. `latent_diffusion/models/.`
     2. `latent_diffusion/modules/diffusionmodules/.`
     3. `latent_diffusion/modules/encoders/.`
     4. `latent_diffusion/modules/phoneme_encoder/.`
     5. `latent_diffusion/modules/attention.py`


3. **问题疑惑与解答**

   - 暂无

### 未来双周计划

1. 继续梳理并转换推理代码的框架
2. 需要转换 flan_t5 的模型代码: <https://github.com/google-research/t5x/blob/main/t5x/examples/t5/network.py>
