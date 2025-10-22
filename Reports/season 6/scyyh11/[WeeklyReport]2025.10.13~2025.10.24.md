### 姓名

黄翊展 scyyh11

### 本双周工作

1. **任务1 - 热身打卡**
   - 完成 Stable-Diffusion 训练推理打卡任务（已收到邮件确认打卡成功）

2. **跟进修复PaddleOCR在ARM64架构下对于过大图像的seg fault的问题**
   - 跟进 https://github.com/PaddlePaddle/PaddleOCR/issues/16609 提出更完善的修复方案，解决ARM64下的seg fault
   - 关联PR：https://github.com/PaddlePaddle/Paddle/pull/75731 https://github.com/PaddlePaddle/Paddle/pull/75716

3. **PaddlePaddle GPU单测修复**
   - PaddlePaddle GPU单测修复 No.1: https://github.com/PaddlePaddle/Paddle/pull/75937
      - 该单测由于其他的代码合入导致出现报错，经过排查后修改对应内容。
   - PaddlePaddle GPU单测修复 No.3: https://github.com/PaddlePaddle/Paddle/pull/75945
      - 该单测本身无报错，只修改了`op_test.py`中的内容来消除废弃警告。

4. **修复矩阵乘法中对1维输入的梯度的错误输出**
   - 在PIR模式下，对1维输入，会错误的返回2维的梯度，导致Dygraph和Static的结果不一致
   - 此bug关联GPU单测修复 No.14: https://github.com/PaddlePaddle/Paddle/pull/75909

5. **修复LogSigmoid算子对复数的支持**
   - 当前`LogSigmoid`算子在进行复数运算时会错误的调用实数相关的计算公式，导致计算结果出错
   - 关联PR: https://github.com/PaddlePaddle/Paddle/pull/75953

### 未来双周计划

1. 跟进未合入的PR
2. 参与其他非热身任务
