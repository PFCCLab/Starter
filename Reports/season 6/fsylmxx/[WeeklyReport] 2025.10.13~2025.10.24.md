### 姓名

恽若溪（fsylmxx）

### 开发中的快乐开源任务
- PaddlePaddle PHI算子库CUDA Kernel规范化https://github.com/PaddlePaddle/Paddle/issues/75226
- Stable-Diffusion 训练推理

### 本双周工作

1. **完成中文文档修复 https://github.com/PaddlePaddle/docs/issues/7543**

   - pr如下：https://github.com/PaddlePaddle/docs/pull/7563。
   - 学习教程如下：https://github.com/PaddlePaddle/Paddle/issues/69442
2. **git的学习**

   - 学习使用 Git 进行版本控制，掌握代码分支管理、合并与冲突解决等操作流程；熟悉通过 Pull Request（PR）进行代码提交与协作评审，提升团队开发效率与代码规范性。

3. **问题疑惑与解答**

   - **问题 a**解决 PR 上传冲突，手动解决冲突
     
     答：当提交 PR 时提示冲突（conflict），说明你的分支与上游仓库（upstream）存在代码差异。可按以下步骤手动解决：

         确保本地已设置上游仓库：git remote add upstream git@github.com:PaddlePaddle/docs.git
         获取最新的上游更新并合并到当前分支：git fetch upstream
                                            git merge upstream/develop
         若出现冲突，打开冲突文件，手动保留正确内容，删除冲突标记（如 <<<<<<<、=======、>>>>>>>）。
         解决后执行：git add .
                     git commit -m "Resolve merge conflicts"
         最后将修改推送至远程仓库：git push origin 分支名
         完成后，在 GitHub 页面刷新 PR 即可看到冲突已解决，等待合并。
### 未来双周计划

1. 继续完成 Stable-Diffusion 训练推理
2. PaddlePaddle PHI算子库CUDA Kernel规范化https://github.com/PaddlePaddle/Paddle/issues/75226

感谢[@Echo-Nie](https://github.com/Echo-Nie)，[@luotao1](https://github.com/luotao1)，[@ooooo-create](https://github.com/ooooo-create)的指导。
