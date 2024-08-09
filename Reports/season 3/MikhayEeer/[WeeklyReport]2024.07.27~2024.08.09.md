### 姓名

邓子立(MikhayEeer)

### 开发中的快乐开源任务

stable diffusion训练
    显存较小，还在进一步调整

### 本双周工作

- 在AIStudio完成了paddlepaddle的编译任务
    打开已通过


### 未来双周计划

1. 继续完成stable diffusion推理
2. 寻找专项团任务

### 任务总结

ai studio部分位置会重置，当日编译完成后就退出关闭ai studio了，次日进入进行make就报错，并且发现有很多python包丢失

指定安装在`-t /home/aistudio/external-libraries`

stable-diffusion在二次开发框架中，安装的paddle一直无法通过`paddle.utils.run_check()`，尝试多种方案，并且多次重装，最后选择新建ai studio项目，选择预装了paddle的项目再进行训练，这次的`paddle.utils.run_check()`通过，并且使用conda创建一个虚拟环境，再进行依赖的安装。使用`train.sh`，部分设定的内容无法被识别，猜测和编码等问题相关，为了优先测试流程能跑通，手动输入命令，不依赖`train.sh`，由于新的项目的GPU是16GB显存，比二次开发框架GPU32GB小，还需进一步调整以适应较小的显存。