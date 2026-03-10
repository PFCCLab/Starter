### 姓名

十月祈雨

### 本双周工作

1. **任务 一 【快乐开源】PaddlePaddle 文档链接修复任务 #7735**

   - 认领完成了 PaddlePaddle 文档链接修复任务 36
   - 提交了对PaddlePaddle/docs仓库的PR
2. **任务 二 【热身打卡】开发框架，从编译 paddle 开始 #45347**

   - 新建云端服务器Ubuntu实例,按照【Linux下使用 make 从源码编译】的步骤进行操作
   - 完成 Paddle 源码拉取,并采用CPU编译方式进行编译
   - 依赖环境配置与初次编译:
     1. 在包含基础pip包的conda环境下通过pip安装必要的工具:bzip2以及make
     2. 通过requirements.txt安装编译依赖
     3. 设置好Python3相关的环境变量 (PYTHON_LIBRARY，PYTHON_INCLUDE_DIRS)
     4. 增加时间戳执行CMake，通过后使用time make -j$(nproc),完成初次编译
   - 二次编译:
     1. 对三个文件分三次进行修改: [底层头文件]enforce.h [Op的cc文件]rank_loss_op.cc [python文件]math.py
     2. 修改一次文件后进行一次二次编译，共三次
     3. 检查时间戳结果并与初次编译进行对比
   - 安装Wheel包:
     1. 在 paddle/build/python/dist 目录下找到whl包并通过pip进行安装
   - 运行单元测试:
     1. 加上 -DWITH_TESTING参数 重新执行除此编译时的CMake命令
     2. 再次进行编译，编译完成后进入build目录 执行单元测试并通过 至此完成所有任务步骤
3. **任务 三 【热身打卡】FastDeploy 编译打卡 #6225**

   - 使用云端V100 GPU进行编译任务,按照【V100 Warmup Tutorial】的步骤进行操作
   - 安装PaddlePaddle
   - 在合适的目录下克隆FastDeploy的源码,同时要注意切换到V100所支持的PR分支，并且在锁定commit后确认commit的预期输出与指定分支一致 (fastdeploy_v100)
   - 执行 FastDeploy 编译与打包:
     1. 确认本次编译构建Wheel 解释器使用Python 不编译CPU算子 并且GPU架构参数为70("[70]")后 执行命令编译FastDeploy源码
     2. 编译完成后，产物位于 FastDeploy/dist/ 目录下
   - 二次编译测试:
     1. 对三个文件分三次进行修改: [kernel_traits头文件]kernel_traits.h [transfer_output的cc文件]transfer_output.cc [python文件]read_ids.py
     2. 修改一次文件后进行一次二次编译，共三次
     3. 检查时间戳结果并与初次编译进行对比
   - 安装Wheel包:
     1. 在 dist 目录下找到whl包并通过pip进行安装
   - 验证V100 支持,是否和预期输出一致:

   ```
   Platform: <fastdeploy.platforms.cuda.CUDAPlatform object at 0x...>
   SM Version: 70
   Is V100 (SM70): True
   ```

   - 运行单元测试:
     1. 使用python运行单元测试通过，至此完成所有任务步骤

### 未来双周计划

1. 完成"PaddlePaddle API兼容性增强"专题中的任务
2. 继续学习 PaddleOCR 内容
3. 继续完成2-3项文档修复任务
