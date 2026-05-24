# C++ |类和对象|问题 4

> 原文:[https://www . geesforgeks . org/c-class-and-object-question-4/](https://www.geeksforgeeks.org/c-class-and-object-question-4/)

以下哪一项是正确的？
**(A)** 一个类的所有对象共享类的所有数据成员
**(B)** 一个类的对象不共享非静态成员。每个对象都有自己的副本。
**(C)** 一个类的对象不共享非静态方法的代码，它们有自己的副本
**(D)** 以上

**都没有答案:****(B)**

**解释:**每个对象都维护一个非静态数据成员的副本。例如，让 Student 是一个类，数据成员为名称、年份、批次。每个学生对象都有自己的名字、年份和批次。另外，静态数据成员在对象之间共享。
所有对象共享所有方法的代码。例如，每个学生对象都使用相同的逻辑来找出分数或任何其他方法。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)