### 姓名

代佳诚(@jiachengdai)

### 开发中的快乐开源任务

热身任务3 Stable-Diffusion 训练推理

### 本双周工作

1. **任务 1 给飞桨 API 文档增加图例，完成你的第一个 PR**

   - 认领scatter的API图例添加任务，并成功合入中、英文文档图例，并通过邮件打卡
   - PaddlePaddle/docs#6973

2. **任务 2 完成Paddle本地编译**

   - 使用AIStudio环境完成Paddle本地编译，成功打卡通过

3. **问题疑惑与解答**

   - 问题 a  AIStudio本地编译时提示Makefile错误

     答：调小编译命令线程数得到了解决

   - 问题 b Stable Difussion 跑模型时，使用预训练提示
     
    ```
     OSError: The file https://bj.bcebos.com/paddlenlp/models/community/stable-diffusion-v1-4/unet/config.json does not exist.!
    There was a specific connection error when trying to load 'stable-diffusion-v1-4/unet'! We couldn't connect to 'https://bj.bcebos.com/paddlenlp' to load this model, couldn't find it in the cached files and it looks like 'stable-diffusion-v1-4/unet' is not the path to a directory containing a file named 'config.json'.
    ```

     答：暂时还没有解决，尝试把模型拉到本地又太大了拉不下来。

### 未来双周计划

1. 继续完成热身任务3
2. 认领提交一项非热身打卡的专向团PR
