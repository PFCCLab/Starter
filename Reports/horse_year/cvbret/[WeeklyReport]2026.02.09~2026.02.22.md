### 姓名 张博诚
### github ID cvbret

### 开发中的快乐开源任务


### 本双周工作

1. **Windows 下从源码编译PaddlePaddle**

   - 完成在Windows下从源码本地编译CPU版本的PaddlePaddle 
   - 掌握Paddle 从 CMake 配置、编译、单元测试到二次增量编译的全流程，理解编译工具（Ninja/CMake/ctest）的协同逻辑
   - 掌握 VS x64 本机工具命令提示符、Ninja、CMake 的组合使用，理解 -DWITH_GPU/-DWITH_TESTING/-DWITH_UNITY_BUILD 等关键 CMake 参数的作用；
   - 用PowShell下的Measure-Command命令实现类似Linux下的time命令，测量编译时间和测试时间
   - 掌握 Windows 下通过 ctest -R 测试名 运行指定单元测试的方法，结合计时工具完成 “测试 + 耗时统计” 的闭环。

2. **通过AutoDL服务器租赁V100 GPU完成FastDeploy的编译和测试**

   - 掌握 AutoDL 云环境的核心操作：
      1. 通过创建 FastDeploy 独立环境实现conda环境隔离，避免与本地环境冲突
      2. nvidia-smi/lscpu命令查看硬件信息
      3. 大文件上传 / 解压
   - 理解 cmake/nvcc 编译参数的意义（time MAX_JOBS=8 bash build.sh 1 python false "[70]" 2>&1 | tee "build_v100_$(date +%Y%m%d_%H%M%S).log"）
      1. MAX_JOBS=8 避免 OOM
      2. [70] 指定 V100 算力
   - 理解.whl包的用途，能够打包源码编译结果，方便在其他环境安装和使用
   - 学会用 pytest 组织单元测试

3. **问题疑惑与解答**

   - 问题1 在进行Windows 下从源码编译PaddlePaddle时遇到了numpy版本过高（numba 0.62.1 要求 numpy 版本在 >=1.22 且 <2.4，但当前安装的是 numpy 2.4.2，版本过高导致不兼容）？

     答：使用pip install numpy==2.3.1命令指定安装兼容版本


   - 问题2 Windows环境下没有类似Linux的time命令打上时间戳？

     答：使用PowShell下的Measure-Command命令实现类似Linux下的time命令，测量编译时间和测试时间

   - 问题3 在进行FastDeploy的编译时，修改不同文件后二次编译时间和初次编译时相近？
     答：是因为FastDeploy的编译是增量编译，只编译修改的文件，其他文件都从缓存中读取，所以二次编译时间和初次编译时相近。

   - 问题4 编译完成后，如何在其他环境安装和使用FastDeploy？
     答：使用pip install fastdeploy-0.0.1-cp310-cp310-win_amd64.whl命令安装.whl包，即可在其他环境使用FastDeploy。


### 未来双周计划

1. 完成最后一个热身任务文档示例代码修复
2. 了解和学习PaddleOCR + ERNIE × Open-Source Ecosystem 高价值开源项目
