### 刘煦东

2024.07.17-2024.07.26

### 开发中的快乐开源任务

文档打卡，PIR 单测推全，报错信息优化，CINN 编译器符号推导扩量

### 本双周工作

1. **任务 1：文档打卡**

   - 描述：提交 1 个PR，并成功合入。
   - PR链接：https://github.com/PaddlePaddle/Paddle/pull/66277

2. **任务 2：PIR 单测推全**

   - 描述：提交 7 个 PR，成功合入 3 个，1 个已经被修复过，1 个移交给王欢老师处理，2 个等待 Merge。
   - PR链接：
     1. https://github.com/PaddlePaddle/Paddle/pull/66222 已合入
     2. https://github.com/PaddlePaddle/Paddle/pull/66226 已合入
     3. https://github.com/PaddlePaddle/Paddle/pull/66468 等待 Merge
     4. https://github.com/PaddlePaddle/Paddle/pull/66287 已合入
     5. https://github.com/PaddlePaddle/Paddle/pull/66365 已移交
     6. https://github.com/PaddlePaddle/Paddle/pull/66377 等待 Merge

3. **任务 3：报错信息优化**
  - 描述：提交 2 个 PR，共计完成 70 个 `CHECK_xx` 宏替换成 `PADDLE_ENFORCE_xx` 的操作，并已全部合入。
  - PR 链接：
    1. https://github.com/PaddlePaddle/Paddle/pull/66507 已合入
    2. https://github.com/PaddlePaddle/Paddle/pull/66518 已合入

4. **任务 4：CINN 编译器符号推导扩量**
  - 描述：提交 1 个 PR，等待 CI 测试，还未合入。
  - PR 链接：
    1. https://github.com/PaddlePaddle/Paddle/pull/66570 未合入

5. **问题疑惑与解答**

   - 问题 1：pre-commit 无法正常运行，在本地环境中检测不到 python 环境。

     答：修改 `Paddle/tools/codestyle/clang_format.sh` 文件和 `Paddle/.pre-commit-config.yaml` 文件中的 `python` 命令为 `python3` 命令。

   - 问题 2：CI 测试经常出现错误，需要多次重测。

     答：可以根据报错日志中的报错信息对应检查自己文件相应位置的错误。

### 未来双周计划

1. 成功将 PIR 单测推全任务中剩下的 2 个 PR 进行 Merge；
2. 完成 CINN 编译器符号推导扩量的 3 个任务；
