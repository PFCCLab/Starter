### 姓名

邓子立(MikhayEeer)

### 开发中的快乐开源任务

跟进符号推导的CI

### 本双周工作

- 完成paddle的本地docker编译
- 提交了符号推导
    [【Infer Symbolic Shape No.77】log_softmax #68025](https://github.com/PaddlePaddle/Paddle/pull/68025)

### 未来双周计划

- 继续专项团任务

### 感悟

之前在aistudio上进行了编译，编译过程很顺利，但是偶尔需要长期挂着且由于关闭重进会丢失一些环境，所以选择了在本地编译一个paddle。
也是为了使用一下docker，就在docker中进行了编译，这个过程持续时间较长，遇到过各类问题。
- 首先是遇到了软链接错误，找不到`data_type_transform.cu`，在这里是直接替换了提到该软链接的`CMakeLists.txt`内容,
- 还有就是较多的`\r`错误，这是由于Windows和Linux的换行符问题，使用命令`vim -b`能够看到行末的`^M`
命令`sed -i 's/\r$//'`进行替换
- 遇到报错
```bash
ERROR: Can NOT import paddle from `tools/gen_tensor_stub.py` before installation. So the stub file `python/paddle/tensor/tensor.pyi` of `paddle.Tensor` may be lost. We COULD import paddle without installation with all libs (.dll or .so) copied into dir `paddle/libs`, or path already been set for the system. 
```
使用命令
```bash
SKIP_STUB_GEN=ON make
```
最后还是编译成功