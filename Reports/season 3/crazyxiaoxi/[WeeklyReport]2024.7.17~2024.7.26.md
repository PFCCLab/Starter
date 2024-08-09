### 姓名

奚嘉文

### 开发中的快乐开源任务

文档打卡任务
PIR单测推全
报错优化任务

### 本双周工作

1. **任务 文档打卡**
    提交1个pr，合入1个
   - 简单的修改了函数调用的类型/python/paddle/check_import_scipy.py


2. **任务 PIR单测推全**
    提交7个pr，合入4个，待测2个，搁置1个
   - 使用if not paddle.framework.use_pir_api(): 解决set_need_check_feed
   - .clone()的某些点在PIR模式下不支持，使用OldIrGuard
   - data_feeder
     1.feeder传入的demension不匹配在feeder加入feed_data函数，来调整输入，适应新版本
     2.而在pirmode下，lod_level并没有定义，因此如果强行append的话会报错,测试结果就应该是[]，而不是[3,2,4]等，对预期的测试结果进行修改
   - str的类型调用有问题
    参考test_function_in_pir将out.name改成out，boxes_num修改格式就可
   - dimension不匹配的问题
    缺失lod_level.append,在reader.py中加入pir模式下进行测试出现了传入参数demension不匹配的问题 改变第二维度 (但注意还有第三维度改变与否无法测试，因为后面报错显示不支持)
    -对于'main_program' in paddle.static.program_guard() 的报错，移除单测。

3.**报错信息优化**
    提交4个pr，合入0个，待测4个
    - 优化报错信息，将报错信息更改为更加明确的信息，将CHECK改成PADDL_ENFORCE
  
1. **问题疑惑与解答**

   - 问题 a: oldguard什么时候可以使用？

     答：测试点必须要在旧版本进行测试的时候，才可以使用oldguard

   - 问题 b: 如何修改报错？

     答：查看报错栈，找到报错的位置，然后根据报错信息进行修改

### 未来双周计划

1. 完成CINN符号任务
2. 修改完成未合入pr
3. 根据任务安排继续完成
