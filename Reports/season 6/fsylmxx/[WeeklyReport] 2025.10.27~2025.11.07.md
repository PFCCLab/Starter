### 姓名

恽若溪（fsylmxx）

### 开发中的快乐开源任务
- PaddlePaddle PHI算子库CUDA Kernel规范化https://github.com/PaddlePaddle/Paddle/issues/75226

### 本双周工作

1. **Stable-Diffusion 训练推理**

2. **Stable-Diffusion原理的学习**

   - https://github.com/PaddlePaddle/PaddleMIX/blob/develop/ppdiffusers/examples/stable_diffusion/README.md
3. **问题疑惑与解答**

   - **问题 a**: 在 Stable-Diffusion 推理时出现 “CUDA out of memory” 报错，导致生成中断。
     
     答：该问题通常由于显存不足引起，特别是在高分辨率生成或 batch size 过大时。
         （1）减少 batch size：逐步减小至 8或 4 张；
         （2）降低生成分辨率：将 height、width 参数改为 512×512 或更低；
         （3）启用显存优化：
             export FLAG_RECOMPUTE=1
             export FLAG_XFORMERS=1
         （4)逐步生成：如果仍显存不足，可拆分图像生成为 patch 或使用 --lowvram 模式运行。
### 未来双周计划

1. 继续PaddlePaddle PHI算子库CUDA Kernel规范化https://github.com/PaddlePaddle/Paddle/issues/75226

感谢[@Echo-Nie](https://github.com/Echo-Nie)，[@luotao1](https://github.com/luotao1)的指导。
