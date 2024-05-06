### 姓名

周高威

### 开发中的快乐开源任务

【PIR团】PIR算子推全和单测修复

### 本双周工作

1. **data_norm_op单测修复**

   - 修复gpu backend的segmentation fault，增加inplace输出

2. **max_abs算子迁移**

   - 完成yaml定义
   - 完成inferMeta定义
   - 完成kernel迁移

3. **问题疑惑与解答**

   - 如何实现在grad算子中原地修改forward的output参数

     答：使用inplace原地修改

### 未来双周计划

1. 完成max_abs算子functor迁移
2. 完成data_norm_op单测修复线上CI提交
