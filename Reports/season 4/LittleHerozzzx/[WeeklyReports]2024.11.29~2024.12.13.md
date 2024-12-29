### 姓名

周鑫

### 开发中的快乐开源任务

1. CINN 编译器后端 Pass 改造之 `RemoveScheduleBlock`
    - https://github.com/PaddlePaddle/Paddle/pull/70038



### 本双周工作

1. **RemoveScheduleBlock Pass 注释添加**

   - 已提交 PR：https://github.com/PaddlePaddle/Paddle/pull/70225

2. **问题疑惑与解答**

   - 如何判断 Pass 级别？
        - 答：理解 Pass 的作用范围，例如如果一个 Pass 需要处理多条 If Stmt，那么这个Pass 显然不是 Stmt 级别，而是 Block 级别。 Stmt 应该只对单挑语句处理。

### 未来双周计划

1. 完成 `RemoveScheduleBlock` Pass。
2. 认领并完成其它一个 Pass 改造任务。（上周进展太太太少了）
