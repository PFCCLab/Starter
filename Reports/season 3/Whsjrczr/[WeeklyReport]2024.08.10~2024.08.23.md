### 姓名

郭宇芯

### 开发中的快乐开源任务

1. TypeHint 类型标注第三批

2. Typing PEP585 Upgrade

3. RUFF 新 rule 引入计划

4. CINN 编译器符号推导扩量 (简单/中等/复杂)

### 本双周工作

1. **TypeHint类型标注第三批**

   重新完成了第三批的 TypeHint 类型标注，涉及 5 个文件，共 9 个

   - C-41, C-42: https://github.com/PaddlePaddle/Paddle/pull/67439 (已merge)

   - C-43, C-44: https://github.com/PaddlePaddle/Paddle/pull/67469 (已merge)

   - C-40: https://github.com/PaddlePaddle/Paddle/pull/67405

2. **Typing PEP585 Upgrade**

   完成 Typing PEP 585 标准集合泛型支持升级任务，共 48 个

   - 101-110: https://github.com/PaddlePaddle/Paddle/pull/67165 (已merge)

   - 111-120: https://github.com/PaddlePaddle/Paddle/pull/67168 (已merge)

   - 121-129: https://github.com/PaddlePaddle/Paddle/pull/67222 (已merge)

   - 131-132, 134-150: https://github.com/PaddlePaddle/Paddle/pull/67229 (已merge)

3. **RUFF 新 rule 引入计划**

   为 Python 端引入 ruff 作为代码风格检查/自动修复工具 的常规更新，共 35 个

   - F[1-10]: https://github.com/PaddlePaddle/Paddle/pull/67264 (已merge)

   - F[11-20]: https://github.com/PaddlePaddle/Paddle/pull/67269 (已merge)

   - F[21-27]: https://github.com/PaddlePaddle/Paddle/pull/67279 (已merge)

   - F[28-35]: https://github.com/PaddlePaddle/Paddle/pull/67277 (已merge)

4. **CINN**

   简单：

   - classcentersample: https://github.com/PaddlePaddle/Paddle/pull/67434

   中等：

   - batch_fc: https://github.com/PaddlePaddle/Paddle/pull/67348 (已merge)

   - bincount: https://github.com/PaddlePaddle/Paddle/pull/67435

   - bmm: https://github.com/PaddlePaddle/Paddle/pull/67431

   复杂：

   - svd: https://github.com/PaddlePaddle/Paddle/pull/67664

   - stft: https://github.com/PaddlePaddle/Paddle/pull/67663

### 未来双周计划

1. 完成 InferSymbolicShape 接口实现