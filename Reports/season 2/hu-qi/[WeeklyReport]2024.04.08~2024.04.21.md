### 姓名

胡琦 (hu-qi)

### 开发中的快乐开源任务

专项团：文档

### 本双周工作

1. **补充 Overview 文档相关 API 描述**

  - 已合入 PR :
        - [Add Overview Doc No.3、4、33-36][1]
  
  - 待提交 PR ：
        - [Add Overview Doc No.5-13]
  
2. **清理未暴露在 sphinx toctree 下的文档**
   
  - 已提交 PR :
        - [Remove File No.10-16、29-32、56-58][2]

3. **趣味项目 [PaddlePaddle-Badge][3]**

  - 缘由： 发现 Astro 社区有这样一个贡献成就查询系统的开源项目，想着能不能用到 PaddlePaddle-Docs 项目中来，用于 Github 首页展示个人在 PaddlePaddle-Docs 项目中的贡献，于是动手 Fork 了项目一顿 CV 操作(Ctrl C + Ctrl V),就有了 [paddlepaddle-badge][4]

  - 效果如下：
    - [![@hu-qi PaddlePaddle contributions](https://paddlepaddle-badge.vercel.app/v1/contributor/hu-qi.svg)](https://paddlepaddle-badge.vercel.app/contributor/hu-qi/)

  - 欢迎定义成就系统，目前的定义在 [achievements.config.ts][5]
  - 当然存在的问题： 数据不全，可能是 Github API 的限制，没办法获取 Paddle 组织下所有项目的统计。
   


4. **问题疑惑与解答**

   - 问题 清理文档时一次提交的内容太多，如何解决 ？

     答：老师建议分多个 PR 提交并注明 PR 描述，如删除/保留的原因、具体路径等。

### 未来双周计划

0. 继续完成`补充 Overview 文档相关 API 描述` 剩下的 devices 相关 API 的 overview 补全
1. 尝试 [为 Tensor API 文档增加图例 ][6]

<!-- ### 参考资料 -->

[1]:<https://github.com/PaddlePaddle/docs/pull/6593> "[Docathon][Add Overview Doc No.3、4、33-36]"
[2]:<https://github.com/PaddlePaddle/docs/pull/6613> "[Docathon][Remove File No.10-16、29-32、56-58]清理未暴露在 sphinx toctree 下的文档 "
[3]:<https://paddlepaddle-badge.vercel.app/> "paddlepaddle-badge 体验地址"
[4]:<https://github.com/hu-qi/paddlepaddle-badge> "hu-qi/paddlepaddle-badge"
[5]:<https://github.com/hu-qi/PaddlePaddle-badge/blob/latest/src/achievements.config.ts> "paddlepaddle-badge 成就系统定义"
[6]:<https://github.com/PaddlePaddle/docs/issues/6614> "为 Tensor API 文档增加图例"