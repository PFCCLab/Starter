### 姓名
涂媛媛
### 开发中的快乐开源任务
1.【Docathon】补充缺失的中文 API 文档（Inplace 类）
2. 完成 Paddle 本地编译
3. Stable-Diffusion 训练推理
### 本双周工作
完成三项热身打卡任务
1.【Docathon】补充缺失的中文 API 文档（Inplace 类）

   - 通过学习https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/dev_guides/api_contributing_guides/api_docs_guidelines_cn.html#api  对API文档修复规则了解更多
   #由于我后期修改时之前的文件已经被修复完成换成了这个
   - https://www.paddlepaddle.org.cn/documentation/docs/en/develop/api/paddle/log__en.html  对于文档中log函数的定义，用法，规则更了解

2. 完成 Paddle 本地编译

   1. 增加时间戳
   2. 初次编译/二次编译
   3. 安装whl包
   #这一步一定要找到准确的目录
   4. 运行单元测试
   #借鉴第三期启航计划完美复刻
   
3. Stable-Diffusion 训练推理
   #消耗时间较长，迭代次数不够，最后使用了训练好的官方数据集
3. **问题疑惑与解答**

   - 问题 Stable-Diffusion在paddle的ai studio上训练需要花费大量的时间消耗大量的算力。

     答：换成了本地和学校服务器

   - 问题 Stable-Diffusion 训练推理过程中环境的要求比较严格，总是在pip install -r requirements.txt时漏一些依赖包，需要后期手动下载特定版本

     答：通过报错提示添加依赖

   - 问题 Stable-Diffusion 训练推理在ai studio和框架二次开发中有时需要管理员权限去解决报错，调试环境，但是没有管理员权限

     答：清除掉现有环境，重新创建环境，十分麻烦

   - 问题 最大的问题是没有足够的算力，不能高速的使用

     答：希望提供一些免费算力在培训期间
### 未来双周计划

1. 学习我喜欢的计算机视角结合自然语言处理
2. 继续深入学习使用sd
3. 完成接下来的PR


