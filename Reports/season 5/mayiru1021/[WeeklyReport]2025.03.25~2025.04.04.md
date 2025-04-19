### 姓名

马乙入

### 开发中的快乐开源任务

-【快乐开源】为 PaddleScience 案例添加 export 和 inference 功能 https://github.com/PaddlePaddle/PaddleScience/issues/788

### 本双周工作

1. **任务 - 热身打卡 **

   - 完成 文档打卡任务（PR 链接：https://github.com/PaddlePaddle/docs/pull/7131）
   - 完成 paddle 本地编译打卡任务（已确认打卡成功）
   - 完成 Stable-Difussion 训练推理打卡任务（已确认打卡成功）

2. **任务 - PaddleScience**

   - 为PaddleScience中N0.34 Fourcastnet 添加export与inference，已基本完成pretrain部分 （PR链接： https://github.com/PaddlePaddle/PaddleScience/pull/1129）

3. **问题疑惑与解答**

   - 问题 Stable-Difussion 训练推理打卡任务时，huggingface_hub版本为0.29.3显示没有cached_download函数？
   答： 似乎是由于0.10.0版本后的huggingface_hub不支持该函数，可以通过修改部分代码解决，在(Reports\season 5\rigidwill666\[WeeklyReport]2025.03.25~2025.04.04.md)中也有提到。

   - 问题 PaddleScience案例fourcastnet中，找不到支持的数据集进行验证的问题？
   答： aistudio中存在对应的案例（https://aistudio.baidu.com/aistudio/projectdetail/6213922?contributionType=1&sUid=455441&shared=1&ts=1684585396793），其中用于验证的数据集直接在数据集中找到，用于数据归一化的数据在项目的data文件夹中，按照路径寻找即可。



### 未来双周计划

1. 根据reviewer的反馈完成No.34剩下部分的export与inference添加，并合入PR。
2. 尝试Paddle Tensor规范化任务二期 或 Paddle算子规范化任务。
3. 学习其他任务 如PaddleX或PaddleMIX。
