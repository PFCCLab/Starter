### 姓名

杨闻宇

### 开发中的快乐开源任务

- 飞桨大模型套件任务，[新增人像美肤模型](https://github.com/PaddlePaddle/PaddleMIX/issues/255)
- 飞桨大模型套件任务，[新增音频生成图像gradio](https://github.com/PaddlePaddle/PaddleMIX/issues/258)

### 本双周工作

1. **完成的任务**

   - 完成了热身打卡任务三，并解决了遇到的问题
   - 完成了热身打卡任务二，发现了[Paddle dev在低版本cuda上的编译问题](https://github.com/PaddlePaddle/Paddle/issues/59675)
   - 完成了新增人像美肤任务 ABPN 论文阅读

2. **正在进行/TODO 的任务**

    - 【新增人像美肤任务】，正在阅读该项目基于Modelscope的源码

3. **问题疑惑与解答**

   - 问题 在AIstudio上从源码编译Paddle dev GPU版报错

     答：具体问题[在 Building paddle/phi/tools/CMakeFiles/print_phi_kernels.dir/all 时报错](https://github.com/PaddlePaddle/Paddle/issues/59675)，经过多次重复实验，确定是可复现的bug，在issue区得到了Paddle的rd回复，可能是在低版本(10.2)的cuda上注册了bf16导致的。

### 未来双周计划

1. 参考PaddleMix已有gradio项目代码和文档，完成【新增音频生成图像gradio】任务
2. 完成ABPN的Modelscope源码阅读
3. 查看paconvert文档和paddle-torch API映射表
