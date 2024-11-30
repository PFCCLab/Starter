### 姓名

崔铭轩（Neo-WY）

### 开发中的快乐开源任务

PaddleMIX：飞桨多模态大模型快乐开源活动LongVA-7B推理，show-o-512x512推理对齐

### 本双周工作

1. **任务 typos工具引入计划**

   - CodeStyle[C-52] Fix typo (`context`) #69839

2. **paddle编译**

3. **Stable Diffusion的跑通**

4. **问题疑惑与解答**

   - 问题 a：安装whl包时按照教程没办法成功安装

   ​       答：python3.7被弃用并且下载方式默认为本地文件

   - 问题 b：Stable Diffusion推理出来的图片是一堆像素点

   ​       答：删除原下载的模型之后，将transformers进行升级，运行eval.py文件即可


### 未来双周计划

1. 模型复现任务：先进行LongVA-7B推理的任务，如果提前完成则继续show-o-512x512推理任务
2. 尝试推进pytorch转paddle任务

