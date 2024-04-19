### 姓名

王赟龙（LittleNoob233）

### 开发中的快乐开源任务

探索团

### 本双周工作

1. **热身打卡任务**

   - 修改飞浆文档
   - 使用AI Studio完成 Paddle 本地编译
   - 在 PaddleMIX 中跑通Stable-Diffusion 的训练推理

2. **报错日志体系优化任务**

   - paddle/cinn/poly/* 进行CHECK_* 宏替换 已提交PR

3. **问题疑惑与解答**

   - 问题 a：在AI Studio上编译paddle源码时报错，AttributeError：module 'numpy' has no attribute 'complex'

     答：升级了numpy对应的版本，已解决问题

   - 问题 b：编译paddle时报错，ModuleNotFoundError：No module named 'ppdiffuers.transformers' 

   ​      答：pip uninstall ppdiffussers然后在ppdiffusers目录 pip install -e . 已解决该问题

   - 问题 c：pre—commit的流程

     答：目前对pre-commit的了解是有一个yaml配置文件,可以详细定制检查项,有一些项是可以自动帮你修改的,此时只需要使用git add .,然后再次commit即可;  
        另外一类是指定某个文件某行有哪些错误,例如我遇到的语法错误,找到对应的文件,然后进行修改即可

   - 问题 d：ai studio 安装慢

     答：使用pip安装东西时,最好是使用百度的镜像源-i https://mirror.baidu.com/pypi/simple/,安装更快,也不会出现找到对应版本的情况


### 未来双周计划

1. 尝试一些其他类型的任务
2. 尝试看paddle
