### 姓名

恽若溪（fsylmxx）

### 开发中的快乐开源任务
- [Docathon] 中文文档格式日常修复 [docs#7435](https://github.com/PaddlePaddle/docs/issues/7435)
- Stable-Diffusion 训练推理

### 本双周工作

1. **完成 Paddle 本地编译**

   - 利用aistudio完成Paddle本地编译。
   - 学习教程如下：https://aistudio.baidu.com/projectdetail/8255767

2. **git的学习**

   - 学习使用 Git 进行版本控制，掌握代码分支管理、合并与冲突解决等操作流程；熟悉通过 Pull Request（PR）进行代码提交与协作评审，提升团队开发效率与代码规范性。

3. **问题疑惑与解答**

   - **问题 a**编译 Paddle 时内存占用过高（内存“爆炸”）

     答：通过减少编译线程数（如使用 make -j4 而非 make -j16）可以显著降低内存占用；同时可关闭部分不必要的编译选项（如 WITH_TESTING=OFF、WITH_DISTRIBUTE=OFF）以节省资源。若在 AI Studio 环境中，可选择更高配置的实例或启用交换分区（swap）以缓解内存不足问题。

   - **问题 b**如何提交 Pull Request（PR）

     答：首先在 GitHub 上 fork 官方 Paddle 仓库，并将其克隆至本地；在本地新建分支并完成代码修改后，通过 git add、git commit、git push 将修改推送至自己的远程仓库；最后在 GitHub 页面上发起 Pull Request，填写修改说明并提交，等待项目维护者审核与合并。

### 未来双周计划

1. 完成打卡 Stable-Diffusion 训练推理
2. [Docathon] 中文文档格式日常修复 [docs#7435](https://github.com/PaddlePaddle/docs/issues/7435)

感谢[@Echo-Nie](https://github.com/Echo-Nie)，[@luotao1](https://github.com/luotao1)的指导。
