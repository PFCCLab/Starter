### 姓名

蔡奕康

### 本双周工作

1. flash_attn_unpadded infer shape：https://github.com/PaddlePaddle/Paddle/pull/67701 
由于这里的infermeta还不完整，涉及的修改比较多；同时paddle.nn.functional中对flash_attn_unpadded的描述也与flash-attention库中不一样，可能需要进一步确定该算子的行为，详见PR
 
### 未来双周计划

继续完成InferShapeSymbolic相关内容:cholesky_solve(中等), solve(复杂)，repeat_interleave_with_tensor_index（复杂）
