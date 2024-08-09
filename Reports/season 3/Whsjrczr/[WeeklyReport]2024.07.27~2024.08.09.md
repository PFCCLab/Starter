### 姓名

郭宇芯

### 开发中的快乐开源任务

1. 文档打卡

2. 报错信息优化第二批

3. TypeHint类型标注第三批

4. Typing PEP585 Upgrade

5. CINN编译器符号推导扩量第一批简单

### 本双周工作

1. **文档打卡**

   完成 Tensor API 文档增加图例

   - squeeze: https://github.com/PaddlePaddle/docs/pull/6802（已merge）

2. **报错信息优化第二批**

   完成第二批的报错信息优化，共16个文件

   - 349-351, 353: https://github.com/PaddlePaddle/Paddle/pull/66832 （已merge）

   - 363-366: https://github.com/PaddlePaddle/Paddle/pull/66872 （已merge）

   - 354, 356, 357, 360: https://github.com/PaddlePaddle/Paddle/pull/66876 （已merge）

   - 362, 368-370: https://github.com/PaddlePaddle/Paddle/pull/66899 （已merge）

3. **TypeHint类型标注第三批**

   完成第三批的TypeHint类型标注，涉及8个文件，共13个

   - C-[25/26], C-[40-44], C-83: https://github.com/PaddlePaddle/Paddle/pull/67203

4. **Typing PEP585 Upgrade**

   完成Typing PEP 585 标准集合泛型支持升级任务，共48个

   - 101-110: https://github.com/PaddlePaddle/Paddle/pull/67165

   - 111-120: https://github.com/PaddlePaddle/Paddle/pull/67168

   - 121-129: https://github.com/PaddlePaddle/Paddle/pull/67222

   - 131-132, 134-150: https://github.com/PaddlePaddle/Paddle/pull/67229

4. **CINN**

   一个算子（cinn_op.uniform_random）搁置，一个算子（class_center_sample）开发中。

### 未来双周计划

1. 完成 Ruff 新 rule 引入计划
2. 完成InferSymbolicShape接口实现