### 姓名

王文杰（smallpoxscattered）

### 开发中的快乐开源任务

专项团：科学计算

### 本双周工作

1. **热身打卡任务**

   - 修改飞浆文档
   - 完成 Paddle 本地编译
   - Stable-Diffusion 训练推理

2. **科学计算 API 文档补全**

   - ppsci.geometry.Mesh下的from_pymesh、scale、translate函数

3. **问题疑惑与解答**

   - 问题 a：编译paddle时，wsl下使用docker直接挂载了windows下的文件系统，导致编译失败。

     答：由于windows和linux文件符号不同，挂载 Linux 文件目录即可解决该问题。

   - 问题 b：修改飞浆文档时，由于输出末尾多了一些空格，pre-commit会消除末尾空格，doctest会检测末尾的空格

     答：在输出后面添加 `# doctest: +NORMALIZE_WHITESPACE` 可以忽略末尾的空格

### 未来双周计划

1. 为 PaddleScience 案例添加 export 和 inference 功能
