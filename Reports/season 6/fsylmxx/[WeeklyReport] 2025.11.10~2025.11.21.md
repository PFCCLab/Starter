
### 姓名

恽若溪（fsylmxx）

### 开发中的快乐开源任务
- PaddleMaterials 数据集适配https://github.com/PaddlePaddle/PaddleMaterials/issues/191

### 本双周工作

1. PaddlePaddle PHI算子库CUDA Kernel规范化
2. 两个PR待审核https://github.com/PaddlePaddle/Paddle/pull/76503/
              https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2204
3. **问题疑惑与解答**

   - **问题 a**: 为什么将 #include "*.cu" 修改为 #include "*.h" 后，必须同步修改 CMakeLists.txt？
                 当直接 include .cu 时，算子实现被包含在当前编译单元中，无需额外配置。改为 include .h 后，注册文件仅包含声明。
### 未来双周计划

1. 修改完善两个PR

感谢[@Echo-Nie](https://github.com/Echo-Nie)，[@luotao1](https://github.com/luotao1)的指导。
