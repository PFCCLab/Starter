### 姓名

胡琦 (hu-qi)

### 开发中的快乐开源任务

专项团：文档

### 本双周工作

1. **热身打卡任务***

   - 修改飞桨文档：了解飞桨 [API 文档书写规范][1]以及[Python 文档示例代码书写规范][2]，实操了文档贡献流程, 文档修复提交部分 PR。

   - 完成 Paddle 本地编译: 尝试在 OpenI 社区算力平台进行编译, 但由于环境和内存溢出问题未编译成功。已申请 AI Studio 资源, 并重新尝试, 已编译成功并邮件反馈.

   - Stable-Diffusion 训练推理: 在 AI Studio V100 32G 的机器上运行成功,遇到 ppdiffusers 版本的问题,尝试切换到 origin/ppdiffusers0.19.4 分支, 成功运行。

2. **文档修复(文档团)**

   - 主要是修复[石墨文档上开发者反馈的历史问题][6]
      - 已合入 PR :

        - 1. [fix: table format when markdown render to html](https://github.com/PaddlePaddle/docs/pull/6568)
        - 2. [fix: paddle-lite docs url](https://github.com/PaddlePaddle/docs/pull/6552)
        - 3. [fix: shimo MODOC 5 7 8 10](https://github.com/PaddlePaddle/docs/pull/6551)
        - 4. [fix: remove Tensor.dist_attr](https://github.com/PaddlePaddle/docs/pull/6548)
        - 5. [fix: Flatten --> Linear](https://github.com/PaddlePaddle/docs/pull/6545)



3. **问题疑惑与解答**

   - 问题 本地源码编译 Paddle 没成功，如何解决 ？

     答：老师建议使用 AI Studio 资源进行编译。最终通过申请 AI Studio 框架开发任务权限,使用 V100 16G 资源成功进行 CPU 环境下源码编译。

   - 问题 PaddleMIX SD 训练&推理时在 AI Studio V100 16G 的机器上无法正常运行,报错内存不足？

     答：使用 V100 32G 环境即可. 参考[跑通 Stable-Diffusion 训练推理][5]

   - 问题 遇到文档中引用源码需要修改的情况，如何修改？比如 [paddle.save][3] 中的代码示例, 文档中引用的是 [PaddlePaddle/Paddle/pthon/paddle/framework/io.py][4]，需要修改 Paddle 仓库吗？

     答：需要

### 未来双周计划

0. 继续跟进[`markdown table 渲染问题`](https://github.com/PaddlePaddle/docs/pull/6568)
1. 尝试[补充 Overview 文档相关 API 描述][7]
2. 尝试处理 [issues][8] 中的问题
3. 尝试参与贡献 [PFCC 社区博客新功能开发][9]

<!-- ### 参考资料 -->

[1]:<https://github.com/PaddlePaddle/docs/blob/develop/docs/dev_guides/api_contributing_guides/api_docs_guidelines_cn.md> "API 文档书写规范"

[2]: <https://github.com/PaddlePaddle/docs/blob/develop/docs/dev_guides/style_guide_and_references/code_example_writing_specification_cn.md> "Python 文档示例代码书写规范"

[3]:<https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/paddle/save_cn.html> "paddle.save"

[4]:<https://github.com/PaddlePaddle/Paddle/blob/develop/python/paddle/framework/io.py#L753> "paddle.save 代码示例源码"

[5]:<https://aistudio.baidu.com/projectdetail/7649127> "跑通 Stable-Diffusion 训练推理"

[6]:<https://shimo.im/sheets/1d3aMbB67WSLEb3g/MODOC> "文档修复(文档团)"

[7]:<https://github.com/PaddlePaddle/docs/issues/6427> "补充 Overview 文档相关 API 描述"

[8]:<https://github.com/PaddlePaddle/docs/issues> "PaddlePaddle/docs issues"

[9]:<https://github.com/PFCCLab/blog/issues> "PFCC 社区博客新功能开发"