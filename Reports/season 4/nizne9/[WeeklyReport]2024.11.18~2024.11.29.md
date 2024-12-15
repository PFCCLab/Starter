### 姓名

钟至佳(@nizne9)

### 开发中的快乐开源任务

暂无

### 本双周工作

1. **热身任务二：拉取 Paddle 代码，完成本地编译**

   - 使用本地 Docker 环境进行 Paddle(CPU) 的编译

2. **热身任务三：在 PaddleMIX 中跑通 Stable-Diffusion 训练推理**

   - 在 AutoDL 上使用 4090 以 bfloat16 完成 Stable-Diffusion 的训练推理

3. **问题疑惑与解答**

   - Paddle 的编译文档 [【Linux 下使用 make 从源码编译】](https://www.paddlepaddle.org.cn/documentation/docs/zh/install/compile/linux-compile-by-make.html) 有缺漏，或者说提供的 Docker 环境有包缺失，无法直接完成编译

     答：自主排查后发现需要安装 networkx，且应用对应的 pip 进行安装


### 未来双周计划

1. 认领一个  [【PaddleMIX 快乐开源活动】](https://github.com/PaddlePaddle/PaddleMIX/issues/787) 的任务
2. 了解一下其他方向
3. 了解 [【CINN编译器后端Pass改造】](https://github.com/PaddlePaddle/Paddle/issues/69639) 的细节并尝试

