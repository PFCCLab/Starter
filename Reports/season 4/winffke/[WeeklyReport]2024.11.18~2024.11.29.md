### 姓名

支韶辉（github ID：winffke）

### 开发中的快乐开源任务

完成 Paddle 本地编译
Stable-Diffusion 训练推理
[CodeStyle][Typos][A-N] ✏️ Typos 工具引入计划

### 本双周工作

1. **任务 1**

   - 利用 AI Studio 完成 PaddlePaddle 编译
   - 基本的指令：
        git clone https://github.com/PaddlePaddle/Paddle.git
        cd Paddle
        pip3.8 install -r python/requirements.txt --user --proxy=oversea-website-proxy.aistudio.public:80（使用代理加速，实测1m/s）
        mkdir build
        cd build
        time cmake .. -DPY_VERSION=3.8 -DWITH_GPU=OFF -DWITH_TESTING=ON
        time make -j$(nproc)
        pip3.8 install /python/dist/paddlepaddle-0.0.0-cp38-cp38m-linux_x86_64.whl
        ctest -R test_logsumexp -V

   -简单陈述遇到的问题：在修改Paddle/paddle/fluid/operators/center_loss_op.cc文件时，发现没有这个文件，并随后，在群里发现有同样问题的人再提问，最后修改了同目录的cc文件。

2. **任务 2**

   - 跑通 Stable-Diffusion 训练推理 
   - 基本的指令：
        git clone https://github.com/PaddlePaddle/PaddleMIX.git
        cd PaddleMIX
        sh build_paddle_env.sh 
        pip install -r requirements.txt --user --proxy=oversea-website-proxy.aistudio.public:80
        pip install ppdiffusers --user --proxy=oversea-website-proxy.aistudio.public:80
        pip install huggingface_hub==0.23.0 --user --proxy=oversea-website-proxy.aistudio.public:80
        # 删除当前目录下的data
        rm -rf data
        # 下载 laion400m_demo 数据集
        wget https://paddlenlp.bj.bcebos.com/models/community/junnyu/develop/laion400m_demo_data.tar.gz
        # 解压
        tar -zxvf laion400m_demo_data.tar.gz
        sh train.sh
        python eval.py

   -陈述遇到的问题： 
    1，在训练营最开始的几天，发现，git到的paddlemix其实是不完整的，比如requestment.txt里面的包和后几天git到的不一样，故容易遇见各种缺包问题。
    2，paddlepaddle下载其实是主目录下的sh文件，但是没有提到，需要在paddlemix的github主页发现，故踩坑
    3，huggingface_hub和ppdiffusers版本不对，尝试很多版本最后解决。
    4，训练程序其实可以设置xxx次训练后保存训练文件，一开始没有设置，干等了很久，故踩坑。


3. **任务 3**

   - [CodeStyle][Typos][A-N] ✏️ Typos 工具引入计划
   - pr：https://github.com/PaddlePaddle/Paddle/pull/69766
        PR Category
        User Experience

        PR Types
        Devs

        Description
        Fix:

        delet
        dependecies
        dependecy
        decprecated
        derivated
        descripor
        deserailize

3. **问题疑惑与解答**

   - 问题 a paddmix的安装包和指令有哪些？

     答：
        sh build_paddle_env.sh 
        pip install -r requirements.txt --user --proxy=oversea-website-proxy.aistudio.public:80
        pip install ppdiffusers --user --proxy=oversea-website-proxy.aistudio.public:80
        pip install huggingface_hub==0.23.0 --user --proxy=oversea-website-proxy.aistudio.public:80

   - 问题 b 在做PIR-TensorRT converter的时候，编译指令是那些？如果不通过该怎么办？

     答：cmake .. -DCMAKE_BUILD_TYPE=Release -DWITH_PYTHON=ON -DWITH_MKL=ON -DWITH_GPU=ON -DON_INFER=ON -DWITH_NCCL=OFF -DWITH_TENSORRT=ON -DWITH_PIP_TENSORRT=ON
         不通过，就删除了/paddle重新跑，经尝试，删除build不一定有用，还是会报错，且不是代码错误，无法解决。
    

### 未来双周计划

1. 目前在做PIR-TensorRT converter的任务，已报名四个，争取完成三个一星，试着挑战另外的一个四星，现在在看已经提交的pr，发现他们的单测代码有很大差异，具体来说，数量不同，命名不同，正在寻找规律；另外，发现Converter的书写不仅需要结合utils的一些函数，还要结合tensorrt的一些函数（可以在nvidia文档查看）。

