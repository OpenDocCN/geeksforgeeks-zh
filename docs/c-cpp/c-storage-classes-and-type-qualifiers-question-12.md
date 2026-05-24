# C |存储类和类型限定符|问题 12

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-12/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-12/)

在 C 语言中，静态存储类不能与:
**(A)** 全局变量
**(B)** 函数参数
**(C)** 函数名
**(D)** 局部变量

**答案:****(B)**

**解释:**将全局变量声明为静态会将其范围限制在其所在的同一文件中
静态函数只能在定义它的同一文件中访问。
声明为静态的局部变量在函数调用之间保留变量的值。