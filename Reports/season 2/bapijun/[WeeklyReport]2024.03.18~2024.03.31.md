### 姓名

吴俊

### 开发中的快乐开源任务

复数支持

### 本双周工作

1. **任务 sparse_abs 

   - 配合review 修改已经提交的pr

2. **任务 sparse addmm coo

   - 提交对应的代码
   -添加单元测试
   -测试前后向

3. **问题疑惑与解答**

   - 问题 在修改addmm中 cusparse 中针对针对spmm的batchsize 貌似存在65535的限制,查看对应的代码,貌似在对应的coo的矩阵中,并不会限制对应的代码,试着测试了一下,如果把三维矩阵拉大,对于addmm超出了batchsize的限制,会导致精度丢失的情况

     答：
    - 问题 还是在addmm中,查看spmm中算法针对csr的采用CUSPARSE_SPMM_CSR_ALG2,,根据文档会导致row-major layout有更优的算法,而针对coo采用了默认算法,是否需要替换成同类型的CUSPARSE_SPMM_COO_ALG4

     答：



### 未来双周计划

1. 跟进sparse addmm
2. sparse addmm csr
3. 非稀疏下addmm