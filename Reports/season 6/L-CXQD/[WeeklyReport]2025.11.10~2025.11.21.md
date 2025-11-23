### 姓名

L-CXQD

### 开发中的快乐开源任务

1. [PaddlePaddle GPU单测修复] - Windows下的test_conv2d_op修复

### 本双周工作

1. [PaddlePaddle GPU单测修复]
   - 完成test_fleet_pyramid_hash的修复：https://github.com/PaddlePaddle/Paddle/pull/76546

    修复旧版 Fleet Transpiler (paddle.incubate.distributed.fleet) 在 PIR 模式下的兼容性问题，并重新启用 test_fleet_pyramid_hash 单测。
    具体修改包括：
    - 移除 clone() 方法中不再支持的 for_test 参数。
    - 在 public.py 和 pserver_pass.py 中增加对 PIR 对象（缺少 type 属性或 append_op 方法）的检查和跳过逻辑。

### 未来双周计划

已完成Windows下的GPU编译，已复现`test_conv2d_op`的报错，正在尝试修复
