### 姓名

fsczz

### 本双周工作

1. **完成热身打卡一**

  - API doc bug修复；
  - PR链接：
    - https://github.com/PaddlePaddle/docs/pull/6320 
    - https://github.com/PaddlePaddle/Paddle/pull/59126
2. **完成热身打卡二**
  
  - 在本地编译Paddle核心框架，成功编译过一次，但再次编译仍然有bug;
  - 使用AI Studio编译Paddle核心框架 。
3. **完成热身打卡三**
  - 使用AI Studio 32G V100进行SD训练推理。
4. **问题疑惑与解答**
  
  - 问题 a：在SD训练过程中出现内存溢出问题？
    
    - 答：使用框架开发项目的16G*2的V100 GPU训练时无论怎么修改参数都会内存不够，需要使用单个GPU内存为32G的V00环境进行训练。
    

### 未来双周计划

1. 完成新IR Python API适配升级的NO. 35、40任务
2. 了解PadlleMIX代码，参与大模型任务
