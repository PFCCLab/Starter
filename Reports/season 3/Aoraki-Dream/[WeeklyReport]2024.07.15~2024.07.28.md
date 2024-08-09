### 姓名

黄弈

### 本双周工作

1. **热身任务 修改飞桨文档**  

   - 完成一项文档图例增加 <https://github.com/PaddlePaddle/docs/pull/6786>

2. **热身任务 paddle编译**  

   - 进行到cmake步骤，出现错误，仍未解决。

3. **问题疑惑与解答**  

   - 问题 cmake步骤克隆失败

    尝试的解决方法：

    - 尝试手动下载库放入third_party目录下  

        结果：执行cmake命令会重新开始克隆，失败
    - 尝试增加缓冲区和手动下库都没有成功  
        结果：报错

        ```
        Cloning into '/home/aistudio/Paddle/third_party/absl'...
        error: RPC failed; curl 56 GnuTLS recv error (-9): A TLS packet with unexpected length was received.
        fatal: The remote end hung up unexpectedly
        fatal: early EOF
        fatal: index-pack failed
        fatal: clone of 'https://github.com/abseil/abseil-cpp.git' into submodule path '/home/aistudio/Paddle/third_party/absl' failed
        Failed to clone 'third_party/absl'. Retry scheduled
        Cloning into '/home/aistudio/Paddle/third_party/absl'...
        error: RPC failed; curl 18 transfer closed with outstanding read data remaining
        fatal: The remote end hung up unexpectedly
        fatal: early EOF
        fatal: index-pack failed
        fatal: clone of 'https://github.com/abseil/abseil-cpp.git' into submodule path '/home/aistudio/Paddle/third_party/absl' failed
        Failed to clone 'third_party/absl' a second time, aborting
        CMake Error at cmake/third_party.cmake:58 (message):
        Failed to update submodule, please check your network !
        ```

### 未来双周计划

1. 解决编译问题
2. 认领任务
3. 开始任务
