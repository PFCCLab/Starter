### 姓名

贺帅帅（shuaihehe）

### 开发中的快乐开源任务

探索团

### 本双周工作

1. **热身打卡任务**

   - 修改飞浆文档，完成第一个 PR
   - 使用AI Studio完成 Paddle 本地编译
   - 在 PaddleMIX 中跑通Stable-Diffusion 训练推理

2. **报错日志体系优化任务**

   - paddle/cinn/lang/目录下进行CHECK_*相关宏替换，已合入PR
   - paddle/cinn/optim/目录下进行CHECK_*相关宏替换，已合入PR

3. **问题疑惑与解答**

   - 问题 a：在AI Studio上编译paddle源码时报错，AttributeError：module 'numpy' has no attribute 'complex'

     答：使用 pip install -U librosa安装 librosa包解决该问题

   - 问题 b：编译paddle时报错，ModuleNotFoundError：No module named 'ppdiffuers.transformers' 

   ​      答：环境版本过旧，pip uninstall ppdiffussers然后在ppdiffusers目录 pip install -e .解决该问题

   - 问题 c：训练Stable-Diffusion内存不足

     答：创建模板任务而不是框架开发任务，使用32G内存的GPU完成训练

   - 问题 d：报错日志体系优化任务提交pr时，ci不过

     答：提交代码之前使用pre-commit检查代码格式，clang-format出现Failed时，代码格式被改动，需要git status查看被改动的文件，并使用git add + 文件名，将代码合并，之后提交正常通过ci测试


### 未来双周计划

1. 完成paddle/cinn/hlir/dialect/*宏替换任务
2. 完成paddle/cinn/pybind/*宏替换任务
3. 尝试报名快乐开源中别的任务