### 姓名

蔡越

### 开发中的快乐开源任务

Kandinsky2.2 训练支持

### 本双周工作

1. **完成热身打卡一二三**
  
  - softmax_with_cross_entropy API doc string格式修复；
  - 本地编译Paddle核心框架；
  - 使用AI Studio 32G V100进行SD训推。
2. **了解Kandinsky2.2 训练支持任务**
  
  - 学习hf/diffusers/example/参考文档Kandinsky2.2，主要包含三部分，1)单机单卡训推；2）单机多卡训推；3）LoRA训推；4)Xformer集成。其中训推理包含两部分，decoder和prior;
  - 学习Kandinsky2.2[设计文档]([kandinsky-community/kandinsky-2-2-decoder · Hugging Face](https://huggingface.co/kandinsky-community/kandinsky-2-2-decoder))，该系统包含多种任务，包含t2i，text-guides i2i, Interpolate，目前与参考文档同步先专注于t2i的训练支持。Kandinsky由子模型CLIP,latent Diffusion, MoVQGAN等组成。
3. **问题疑惑与解答**
  
  - 问题 a：在SD训练过程中找不到unet config配置文件，无法下载模型权重，请求的unet*/config.json URL在云端找不到对应资源(404)？
    
    答：解决问题的方式是避开这个问题，在*/script/prepare.sh中利用命令手动下载模型权重到本地。
    
  - 问题 b：SD训练过程中使用二次开发框架单卡或双卡16G训练，无论bs多小均出现OOM问题？
    
    答：向强大的群友学习，改用经典开发环境中的单卡32G就好了。为什么在二次开发框架会这样，以后是不是不敢用了。
    

### 未来双周计划

1. 继续了解Kandinsky由子模型的具体构成，以其ppdiffusers中与其相关的pipeline，特别是decoder和prior,尝试单机单卡下Pokemon训推;
2. 学习并实践同目录下其他example([如Text2Image](https://github.com/PaddlePaddle/PaddleMIX/tree/develop/ppdiffusers/examples/text_to_image))的代码实现和文档；
3. 怎么使用LoRA? 以及在paddle训推流程中怎么集成Xformer。
