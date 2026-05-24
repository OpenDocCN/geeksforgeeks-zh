# C |存储类和类型限定符|问题 14

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-14/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-14/)

如果:
第 1 行被“auto int a = 1”替换，给定的代码 d\segment 会产生什么输出
第 2 行替换为“寄存器 int a = 2；”(GATE CS 2012)
T3(A)3 1
4 1
4 2
T8(B)4 2
6 1
6 1
T13】(C)4 2
6 2
2 0
8】(D)4 2
4 2
2 0

**回答:** **(D)**

**说明:**如果把第 1 行换成“auto int a = 1；”和第 2 行的“寄存器 int a = 2；”，则“a”在 prtFun()中变为非静态。第一个 prtFun()的输出保持不变。但是，第二个 prtFun()调用的输出会随着第二个调用中创建的“a”的新实例而改变。于是“4 2”又被打印出来了。最后，main 中的 printf()将打印“2 0”。使“a”成为寄存器变量不会改变输出中的任何内容。

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)