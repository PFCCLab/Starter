### 姓名

谢润明

### 本双周工作

1. 完成打卡 Stable-Diffusion 训练推理

2. PaddlePaddle PHI算子库CUDA Kernel规范化

   [【CUDA Kernel No.12】fused_stack_transpose_quant算子Kernel修复 by youge325 · Pull Request #2045 · PaddlePaddle/PaddleCustomDevice](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2045)

   [【CUDA Kernel No.21】ap_facade算子Kernel修复 by youge325 · Pull Request #2046 · PaddlePaddle/PaddleCustomDevice](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2046)

   [【CUDA Kernel No.10】fused_softmax_mask算子Kernel修复 by youge325 · Pull Request #2072 · PaddlePaddle/PaddleCustomDevice](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2072)

   [【CUDA Kernel No.22】ap_trivial_fusion_begin算子Kernel修复 by youge325 · Pull Request #2073 · PaddlePaddle/PaddleCustomDevice](https://github.com/PaddlePaddle/PaddleCustomDevice/pull/2073)

3. 将 [fix bugs when compiling with VS2022 by youge325 · Pull Request #75611 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75611) 和 [fix cuda kernel test for windows on cuda13 by youge325 · Pull Request #75684 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75684) 拆分为多个pr，并关联 [paddle.utils.run_check()报错 · Issue #75848 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/issues/75848) ，如下：

   [add support for CUDA 13 on Windows by youge325 · Pull Request #75654 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75654)

   [[Bug fix\] Fix isinf misidentifying NaN as Inf in bfloat16.h by youge325 · Pull Request #75807 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75807)

   [[Bug Fix\] Allow float16/bfloat16 Scalar to be converted to complex types by youge325 · Pull Request #75808 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75808)

   [[Bug Fix\] add missing header include in ir_context.h by youge325 · Pull Request #75927 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75927)

   [[Bug Fix\] Support casting lightweight float formats to complex types by youge325 · Pull Request #75929 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75929)

   [[Bug Fix\] Fix CastKernel for low-precision to complex type conversions by youge325 · Pull Request #75930 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75930)

   [[Bug Fix\] Fix warnings related to deprecated std::iterator usage in elementwise_base.h by youge325 · Pull Request #75931 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75931)

   [[Bug Fix\] Fix C2593 error on MSVC for bfloat16 in RemainderGradDy by youge325 · Pull Request #75932 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75932)

   [[Bug Fix\] Support isfinite/isnan/isinf for float16/bfloat16 on CUDA/HIP by youge325 · Pull Request #75933 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75933)

   [[Bug Fix\] Fix CastDataTypeFunctor for low-precision floats to complex types by youge325 · Pull Request #75934 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75934)

   [[Bug Fix\] Fix NaN/Inf check to support float16, bfloat16, and complex types by youge325 · Pull Request #75935 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75935)

   [[Bug Fix\] Fix missing header include in activation_offloader.h by youge325 · Pull Request #75936 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75936)

   [[Bug Fix\] Improve error handling and compatibility in TensorRT engine tests by youge325 · Pull Request #75948 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75948)

   [[Bug Fix\] Fix compilation issues in enforce_test.cc for different cuFFT versions by youge325 · Pull Request #75949 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75949)

   [[Bug Fix\] Fix CUDA 13.x library loading and installation dependencies by youge325 · Pull Request #75950 · PaddlePaddle/Paddle](https://github.com/PaddlePaddle/Paddle/pull/75950)

### 未来双周计划

1. 继续合入PaddleCustomDevice仓库，争取合入所有剩余pr

2. 已经找到vs2019的安装包，尝试转到vs2019进行之后的工作