### 姓名

MerlinSMQWQ

### 开发中的快乐开源任务

- 【快乐开源】PaddlePaddle 文档链接修复任务

### 本双周工作

1. **【快乐开源】PaddlePaddle 文档链接修复任务**

  - 认领了 PaddlePaddle 文档链接修复任务7
  - 提交PR：[Doc Link Fix No.7](https://github.com/PaddlePaddle/docs/pull/7769) 等待审核
  - 步骤：
    1. 查看需要修改哪些链接，找到正确的链接，进行替换
    2. 按照格式要求提交 commmit
    3. 提交PR并等待审核通过
  - 收获： 熟悉了给大型项目做贡献的流程，为开源社区贡献经历开了个好头

2. **【热身打卡】开发框架，从编译 paddle 开始**

  - 教程链接： [Linux 下使用 make 从源码编译](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/install/compile/linux-compile-by-make.html)
  - 租赁算力云服务器Linux实例完成 paddle 的编译
  - 步骤:
    1. 在云服务器上使用conda创建一个虚拟环境
    2. git clone paddle 仓库到本地
    3. pip install -r requirements.txt 安装项目所需要的依赖
    4. 检查环境是否符合要求，例如检查 gcc 版本，我遇到了版本过高的问题
    5. 进行 cmake
    6. 进行 make
    7. 如果 make 中途发生了报错，需要处理报错
    8. 进行二次编译
    9. 安装编译得到的 whl
    10. 进行测试，并得到测试结果
    11. 总结并发送邮件
  - 收获：熟悉了这种大型框架的编译流程，也学习了如何解决一些编译中可能遇到的问题，还学习了如何处理 git 网络问题，并且帮助其他同学解决遇到的类似问题，提升了解决问题的能力，也提升了团结协作的能力

3. **【热身打卡】FastDeploy 编译打卡**

  - 教程链接：[FastDeploy V100 热身打卡教程](https://github.com/mattheliu/Paddle-Tutorial/blob/main/FastDeploy/warmup/V100_Warmup_Tutorial.md)
  - 租赁算力云服务器Linux实例完成 FastDeploy 编译
  - 步骤：
    1. 租赁一台 V100 服务器，并且检查cuda版本
    2. 使用 conda 创建一个虚拟环境
    3. 安装对应版本的 paddle
    4. git clone FastDeploy 将仓库克隆到本地，并且切换到对应的分之以及对应的 commit 上去
    5. pip install -r requirements.txt 安装相应的依赖
    6. 使用已经写好的 build.sh 脚本进行编译，通过日志分析错误并修复错误
    7. 进行二次编译
    8. 安装 whl
    9. 验证 V100 支持
    10. 使用 pytest 进行单元测试
    11. 总结并发送邮件
  - 获取：了解了 FastDeploy，并且可以更熟练地解决依赖问题，帮助同学并一起讨论。

4. **问题疑惑与解答**

  - 拉取仓库的时候遇到网络问题怎么办？

    答：autodl 提供了学术加速服务，如果还是无法解决，可以考虑换源或者上传仓库并切换到对应的commit。

  - 总是因为环境问题报错？

    答：更加推荐使用 conda 并且一定不要忘记安装依赖！检查 python 版本 gcc 版本和 cuda 版本等。

  - 内存不足？

    答：我测试 FastDeploy 在8线程和10线程的时候最多差不多都是15GB的内存占用，所以确保内存高于这一阈值，不过也可以自己分配虚拟内存，勉强度过短暂的极高内存占用时期。

  - Docker 还是本地编译？

    答：尽量 Docker 吧，如果不想折腾的话。

### 未来双周计划

  - 尝试完成一次 [PaddlePaddle API兼容性增强](https://github.com/PaddlePaddle/Paddle/issues/76301#top) 任务
  - 继续学习 Paddle 框架以及深度学习相关的知识
