### 姓名

钱锦一

### 开发中的快乐开源任务

【HACKATHON 预备营】飞桨启航计划集训营（社团版） #76500

### 本双周工作

1. **文档示例代码修复**

   - [CodeStyle][Xdoctest][206] Fix example code(`paddle.sparse.deg2rad`, `paddle.sparse.rad2deg`) #76632

2. **完成 Paddle 本地编译**

   - 已在本地完成 Paddle 编译，通过邮件提交记录

3. **问题疑惑与解答**

   - 对于 CodeStyle 的修复一开始并不完全，通过 @ooooo-create 的知道了解了正确的修改方向

     答：`core.VarDesc.VarType` 需要进行修改，改成 `core.DataType.FLOAT32`，而且 `_int_dtype_` 里面的内容也是如此，需要修改成对应 `core.DataType` 的类型

### 未来双周计划

1. Stable-Diffusion 训练推理
2. 修复更多 CodeStyle 问题
3. 完成专题任务
