### 姓名

王文杰（smallpoxscattered）

### 开发中的快乐开源任务

专项团：科学计算

### 本双周工作

1. **为 PaddleScience 案例添加 export 和 inference 功能**

    - fsi/viv.py 已合入

2. **问题疑惑与解答**

    - 多个算子中，其中一个算子报错，该如何定位到那个算子报错
        答：可以使用try: 报错那一行代码，except 中使用pdb

    - 直接拿普通函数用 setattr 重新定义类函数时，导出时，func(self, *args, **kwargs)报错（func-->类函数, self-->实例，后面是函数参数）
        答：新定义的函数需要多增加一个实例作为输入

### 未来双周计划

1. 为 PaddleScience 案例添加 export 和 inference 功能
