### 刘煦东

2024.07.27-2024.08.09

### 开发中的快乐开源任务

报错信息优化第二批，CINN 编译器符号推导扩量，Ruff 新 rule 引入计划第二期

### 本双周工作

1. **任务 1：报错信息优化第二批**

   - 描述：提交 5 个PR，并全部成功合入。
   - PR链接：
     1. https://github.com/PaddlePaddle/Paddle/pull/66700 已合入
     2. https://github.com/PaddlePaddle/Paddle/pull/66719 已合入
     3. https://github.com/PaddlePaddle/Paddle/pull/66733 已合入
     4. https://github.com/PaddlePaddle/Paddle/pull/66739 已合入
     5. https://github.com/PaddlePaddle/Paddle/pull/66789 已合入

2. **任务 2：CINN 编译器符号推导扩量**

   - 描述：提交 5 个 PR，成功合入 3 个，1 个等待导师review，1 个等待debug。
   - PR链接：
     1. https://github.com/PaddlePaddle/Paddle/pull/66570 已合入
     2. https://github.com/PaddlePaddle/Paddle/pull/66579 已合入
     3. https://github.com/PaddlePaddle/Paddle/pull/66606 已合入
     4. https://github.com/PaddlePaddle/Paddle/pull/67206 等待review
     5. https://github.com/PaddlePaddle/Paddle/pull/67121 等待debug

3. **任务 3：Ruff 新 rule 引入计划第二期**
  - 描述：提交 7 个 PR，共计完成 56 个文件的 `RUF005` 规则修复的操作，并已全部合入。
  - PR 链接：
    1. https://github.com/PaddlePaddle/Paddle/pull/67122 已合入
    2. https://github.com/PaddlePaddle/Paddle/pull/67130 已合入
    3. https://github.com/PaddlePaddle/Paddle/pull/67139 已合入
    4. https://github.com/PaddlePaddle/Paddle/pull/67153 已合入
    5. https://github.com/PaddlePaddle/Paddle/pull/67187 已合入
    6. https://github.com/PaddlePaddle/Paddle/pull/67191 已合入
    7. https://github.com/PaddlePaddle/Paddle/pull/67194 已合入

4. **问题疑惑与解答**

   - 问题 1：pre-commit 无法正常运行，在本地环境中检测不到 python 环境。

     答：在 Vscode 中创建一个 python 的虚拟环境 venv，在该环境中可以成功进行 pre-commit 操作。

   - 问题 2：CINN 任务中的部分算子缺少 OpTest 文件或者函数，需要我们手动添加。

     答：可以尝试根据类似的算子的 OpTest 函数模仿撰写代码，添加 check\_output 函数，更困难的情况可以及时求助导师。

   - 问题 3：CINN 任务中，InferSymbolicShape 函数的 DimExpr 类型参数不能直接进行大小的比较。

     答：可以通过调用 DimExprBuilder 类中的函数 Min，Max 来获取两个 DimExpr 参数的最大值或最小值；但如果我们希望在编译的过程中仍能实现大小的比较可以通过调用 DimExpr 参数的具体类型（例如：转成 int 类型参数）来进行大小的比较，当然前提是需要 DimExpr 参数可以转换为 int 类型的参数。


### 未来双周计划

1. 合入 CINN 编译器符号推导扩量最后 2 个PR。