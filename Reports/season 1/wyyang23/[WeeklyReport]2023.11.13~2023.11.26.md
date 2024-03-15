### 姓名

杨闻宇

### 开发中的快乐开源任务

飞桨大模型套件任务，[新增人像美肤模型](https://github.com/PaddlePaddle/PaddleMIX/issues/255)

### 本双周工作

1. **任务 X**

   - [完成热身打卡任务一](https://github.com/PaddlePaddle/docs/pull/6332)
   - 初步完成热身打卡任务三，但是没有训练完成，没有卡时了

2. **任务 Y**

   - 完成热身打卡任务2：利用 AI Studio 完成 Paddle 框架二次开发编译
   - 在PaddleMiX中新增人像美肤模型:
     1. 阅读论文
     2. 阅读源码
     3. 根据代码进行权重以及网络结构转换
     4. 验证模型，仅要求前向推理输出结果一致。
     5. 提交代码

3. **问题疑惑与解答**

   - 问题1 关于在vscode上用reStructuredText渲染预览rst文档时出现的bug？

     答：未找到解决方案。reStructuredText插件有两种渲染引擎 docutils 和 spinx + esboni 方案，但第二种用esboni LSP的问题太多了，总是有莫名其妙的库需要安装，安装又是一堆兼容问题，可能和它的conf配置有关，遂用第一种docutils，但是也有问题，大部分可预览了，但是".. py:function::paddle.gather()的解析出错了，还有后面的"ref 其他docs"的出错了

   - 问题 在AIstudio跑热身打卡三的问题？

     答：
     1. 训练脚本出现命令*not found*错误，在shell中查看时"train.sh"脚本的fileformat = dos，而且中间有空行，所以linux系统识别不了；
     2. 在pip install requestment.txt时，有模块Steamlit不兼容，查他的文档，然后更新它就不报错了
     3. 在推理时，直接在notebook中运行推理代码报错"ppdiffusers not found"，发现pip安装的path和jupyter的path不同，然后改成py脚本，在shell中运行就可以了
     4. 缺少卡时，diffusion model的**训练未完成**，希望可以发放算力卡。

### 未来双周计划

1. 等AIstudio的框架二次开发申请通过后，完成paddle的二次编译开发任务
2. 阅读人像美肤论文
3. 学习paddle论文复现流程
