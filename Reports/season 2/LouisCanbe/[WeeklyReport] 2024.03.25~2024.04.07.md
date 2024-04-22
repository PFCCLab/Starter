### 姓名

吴小龙（LouisCanBe）

### 开发中的快乐开源任务

热身任务：2.完成 Paddle 本地编译
3.Stable-Diffusion 训练推理

### 本双周工作

1. **任务 《文档修复（文档团）》**

   - 修改了文档中一处错误'bia'->'bias_info'，提交了第一个 PR。
   - 根据任务表格，继续完成文档修复任务。

2. **关于给文档增加 overview 的任务 学习**

   - 说明issue： [【Docathon】补充Overview文档相关API描述 #6427](https://github.com/PaddlePaddle/docs/issues/6427 '未来双周工作')
     1. 阅读函数方法文档，了解各个函数的作用。
     2. 整理文档，增加 overview。
     3. 提交 PR。

3. **问题疑惑与解答**

   - 问题 如何正确签署CLA？遇到的问题？
   - 答：
    1. 【问题场景】提交 PR 的时候，会提示需要签署CLA。显示要添加邮箱，但添加了邮箱之 后，还是提示需要签署CLA。
    2. 【bug】提交commits 的时候，`git config user.email`设置的邮箱不是GitHub账户绑定的邮箱/邮箱和GitHub账户绑定的邮箱不一致/Github未设置邮箱。
    3. 【解决】
        - 在本地设置邮箱，`git config user.email`设置为GitHub账户绑定的邮箱。
        - 确认邮箱：`git config --global user.email`（全局设置）和`git config user.email`（当前仓库设置）。
        - 提交commits：`git commit -m 'xxx' --amend --reset-author`。
        - 提交PR：`git push --force origin branch_name`。
        - 或者：关掉PR，确认本地邮箱后重新commit，重新提交PR。


### 未来双周计划

1. 尝试参与overview文档的编写。
2. 完成热身任务打卡
3. 学习飞桨文档
