### 姓名

周鑫

### 开发中的快乐开源任务

1. 【开源任务】CINN编译器后端Pass改造
   - https://github.com/PaddlePaddle/Paddle/pull/70437
   - https://github.com/PaddlePaddle/Paddle/pull/70462



### 本双周工作
1. 【开源任务】CINN编译器后端Pass改造

   - https://github.com/PaddlePaddle/Paddle/pull/70406
   - https://github.com/PaddlePaddle/Paddle/pull/70334

2. **问题疑惑与解答**
   - 何时使用Mutator、何时使用PassMgr 对 IR 进行遍历？
     - PassMgr 采取 DFS 且先访问子节点的方式进行遍历，而 Mutator 可以实现自定义的遍历顺序；
     - 由此引申出两种不同的 Pass 编写范式：一种是基于 PassMgr，Pass只处理单个节点，例如 正在做的 LongLong2Int；另一种是基于 Mutator，Pass 处理多个节点，例如在RemoveScheduleBlock 中，使用 ReplaceVarWithExprMutator 替换变量；
     - 由于 PassMgr 必定会遍历整个IR，因此第二种方式注定会引入重复遍历的额外开销，只能在开发过程中将Mutator限制在最小范围内。

### 未来双周计划

1. 完成正在开发的两个任务；
2. 认领更多任务，争取与 @Albresky 一道完成所有 CINN 编译器后端 Pass 改造任务；
3. 整理一下在启航计划中的收获，输出为博客。
