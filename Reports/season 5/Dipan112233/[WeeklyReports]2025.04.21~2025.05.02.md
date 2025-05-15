### 姓名  
狄攀

### 开发中的快乐开源任务  
- 进行PaddlePaddle 编译热身打卡活动，运行cmake .. -DPY_VERSION=3.10 -DWITH_GPU=ON -DPYTHON_EXECUTABLE=$(which python) -DPYTHON_INCLUDE_DIR=$(python -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())") -DPYTHON_LIBRARY=$(python -c "import sysconfig; print(sysconfig.get_config_var('LIBDIR'))") 而能出结果，不在报错，在跑make -j$(nproc)，但报错了,gpt说内存不足，之后拿2卡试试

### 本双周工作  

1. **任务 删除被弃用的API**

    - 搭建好编译环境；
    - 解决编译所遇到的一些问题；
    - 理解二次开发模式，dock环境的作用：不需要前面自行配置很多，直接导入根本paddlepaddle 

3. **问题疑惑与解答**

- 对编译的流程细节没理解

### 未来双周计划 

- 完成 Paddle 本地编译
- 完成一项 PaddlePaddle

