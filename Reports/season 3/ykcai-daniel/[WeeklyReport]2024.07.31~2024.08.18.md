### 姓名
蔡奕康

### 开发中的快乐开源任务

1. flash_attn_unpadded InferSymbolicShape: 在Paddle的实现中（paddle.nn.functional），flash_attn_unpadded中q,k,v与flash_attn不同，为三维tensor，其中第一维为total_sequence_length,而flash_attention为batch_size,和sequence_length。 需要根据flash_attn_unpadded的逻辑，在binary_inter_sym中实现shape infer的功能


2. Coverage中/test/custom_op下的测试：这些测试主要和自定义op相关，其中自定义了一个RELU的op，并包括cpu,gpu等实现，在测试中，会先安装对应的egg文件，编译及测试比较复杂。现在已经解决编译问题，已复现问题。

### 未来双周计划

完成上述两个任务，认领其他InferSymbolicShape相关任务