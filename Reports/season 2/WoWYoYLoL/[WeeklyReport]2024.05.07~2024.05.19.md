### 姓名

吴奕琳（WoWYoYLoL）

### 开发中的快乐开源任务
无

### 本双周工作

1. **完成【为hpinns添加export和inference功能】任务，熟悉了模型导出和推理的过程**
2. **调整借助gpt生成API图例的prompt，总结出了一个作图效果比较好的prompt模板**
   
    - 多次调整过程中发现：作图效果好的关键在于明确希望成图的类型（“散点图/热力图”“三维图/平面图”等）
    - 后续优化时可以在prompt中额外指定颜色、间距和数据标签等细节让图片更美观

3. **问题疑惑与解答**

    - 问题：模型推理过程中报错“The variable named x is not found in the scope of the executor”

        答：推理过程基于export模块导出的参数，要注意模型导出和推理模块的输入输出变量相匹配（特别是当前模型有input和output transform时）


### 未来双周计划

1. 再完成1个【添加export和inference功能】的任务
2. 尝试其他方向的任务