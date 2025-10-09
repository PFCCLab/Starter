### 姓名

黄翊展 scyyh11

### 开发中的快乐开源任务

PaddlePaddle GPU单测修复

### 本双周工作

1. **任务1 - 热身打卡**
   - 完成文档打卡任务（PR 链接：https://github.com/PaddlePaddle/docs/pull/7513）
   - 完成 paddle 本地编译打卡任务（已收到邮件确认打卡成功）

2. **任务2 - Docathon中文文档格式日常修复**
   - [Docathon] 中文文档格式日常修复 No.37,38：https://github.com/PaddlePaddle/docs/pull/7513


3. **任务3 - PaddlePaddle GPU单测修复(进行中)**
   - PaddlePaddle GPU单测修复 No.1: https://github.com/PaddlePaddle/Paddle/pull/75553


4. **修复softplus激活函数的复数支持**
   - 完善softplus激活函数对复数的运算：https://github.com/PaddlePaddle/Paddle/pull/75484

5. **修复复数log二阶导数计算错误**
   - 修复log二阶导数对复数的计算错误：https://github.com/PaddlePaddle/Paddle/pull/75463

6. **修复PaddleOCR在macOS对于过大图像的seg fault的问题**
   - 通过调整 `im2col_common` 中索引的计算顺序避免在 `im_row_idx` 或 `im_col_idx` 越界时发生潜在的越界访问/未定义行为: https://github.com/PaddlePaddle/Paddle/pull/75261
   - 关联的issue：
        1. https://github.com/PaddlePaddle/PaddleOCR/issues/16531
        2. https://github.com/PaddlePaddle/PaddleOCR/issues/16457
        3. https://github.com/PaddlePaddle/PaddleOCR/issues/16055

### 未来双周计划

1. 跟进GPU单测修复No.1，根据comment修改代码
2. Stable-Diffusion 训练推理
3. 找机会完成其他的非热身任务
