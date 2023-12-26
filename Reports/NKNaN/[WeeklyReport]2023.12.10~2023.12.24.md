### 姓名

NKNaN

### 开发中的快乐开源任务

AudioLDM2模型复现前向推理

### 本双周工作

1. **大模型快乐开源任务**

   - 阅读 [AudioLDM2 代码](https://github.com/haoheliu/AudioLDM2)，已初步完成 AudioLDM2-full 的模型转换，并对齐了各个子模块的精度，
     其子模块包括：CLAP，FlanT5，AudioMAE，GPT2，Transformer Unet 以及 AutoEncoderKL。
   - 其中除 FlanT5 的模型结构对应 paddlenlp 中已有的 t5-v1_1 模型外，其他模型均需要额外转换，原始代码分别来自：
     - CLAP：<https://github.com/haoheliu/AudioLDM2/tree/main/audioldm2/clap>
     - AudioMAE: <https://github.com/haoheliu/AudioLDM2/tree/main/audioldm2/latent_diffusion/modules/audiomae>
     - GPT2: <https://huggingface.co/gpt2>
     - Transformer Unet: <https://github.com/haoheliu/AudioLDM2/tree/main/audioldm2/latent_diffusion/modules/diffusionmodules>
     - AutoEncoderKL: <https://github.com/haoheliu/AudioLDM2/tree/main/audioldm2/latent_encoder>
     在 CLAP 中还需要用到 roberta-base 模型，由于 paddlenlp 中的该模型与原代码给出的参数不一致，该模型仍需转换：<https://huggingface.co/roberta-base>
   - 已在 AI Stuidio 上跑通了 text-to-audio 任务的推理，效果与原代码相当。


2. **问题疑惑与解答**

   - 暂无

### 未来双周计划

1. 进一步将模型封装，与 paddlemix 中的其他案例保持一致
