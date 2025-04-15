### 姓名

王鑫

### 开发中的快乐开源任务

【Docathon】补充缺失的中文 API 文档（Inplace 类）

【热身打卡】开发框架，从编译 paddle 开始


### 本双周工作

1. **任务 - 热身打卡**

   - 提交文档打卡任务（PR 链接：https://github.com/PaddlePaddle/docs/pull/7234 ）
   - 完成 Stable-Difussion 训练推理打卡任务

2. **问题疑惑与解答**

   - 问题 Stable-Difussion运行中cached_download函数无法导入

     答：在huggingface_hub 0.26 中移除了cached_download，可修改代码，使用hf_hub_download代替，或回退至0.25.2 ，示例代码：`pip install huggingface_hub==0.25.2 -i https://pypi.tuna.tsinghua.edu.cn/simple`

### 未来双周计划

1. 完成 paddle 本地编译打卡任务
2. 尝试 PaddleNLP 相关任务
