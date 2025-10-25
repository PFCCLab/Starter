### 姓名

廖雨菲

### 开发中的快乐开源任务

- 7 test_logical_op[(【启航计划】PaddlePaddle GPU单测修复 · Issue #75208 )](https://github.com/PaddlePaddle/Paddle/issues/75208)

### 本双周工作

1. **任务 [Docathon] 中文文档格式日常修复 #7435**

   - 修复的文档：[hfft_cn](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/paddle/fft/hfft_cn.html)、[irfftn_cn](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/paddle/fft/irfftn_cn.html)、[irfft_cn](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/paddle/fft/irfft_cn.html)。
   - **术语统一优化**
     - 涉及文件：`docs/api/paddle/fft/hfft_cn.rst`、`docs/api/paddle/fft/irfft_cn.rst`、`docs/api/paddle/fft/irfftn_cn.rst`
     - 具体操作：将 3 个 API 文档中的 “傅立叶” 统一替换为规范术语 “傅里叶”，确保文档术语一致性。
   - 移除文档中不必要的换行符，优化内容排版紧凑性，提升阅读体验。

2. **【热身打卡】开发框架，从编译 paddle 开始 #45347**

   按照要求，完成了paddle的本地编译
   
2. **【PaddleMIX 热身打卡】跑通 Stable-Diffusion 训练推理 #273**

    按照要求，跑通了Stable-Diffusion 训练推理
   
4. **问题疑惑与解答**

   - **问题 a ？**编译paddle时，在某个地方，终端长时间没有输出更新，是否是正常现象？

     **答：**因 WSL+Docker 环境下 Windows 挂载目录 IO 延迟、编译后期链接阶段无输出且耗时，及多线程资源竞争导致；等待后正常完成了编译。

   - **问题 b？**如何处理PR冲突？

     **答：**同步上游docs文档`develop`分支时，冲突涉及 hfft_cn.rst、irfft_cn.rst、irfftn_cn.rst 3 个文件，保留修改，删除冲突标记后再进行提交。

### 未来双周计划

1. 完成认领的7 test_logical_op任务(【启航计划】PaddlePaddle GPU单测修复 · Issue #75208 )。
2. 学习多文档智能分析与问答系统相关内容(PaddleOCR + ERINE 案例教程征集 #16454)。

