# 与 C/C++ 中程序编写风格相关的事实和问题

> 原文:[https://www . geesforgeks . org/facts-and-question-to-style-writing-programs-in-c/](https://www.geeksforgeeks.org/facts-and-question-related-to-style-of-writing-programs-in-c-c/)

这里有一些关于 C 程序编写风格的问题:
 **问题-1:** 为什么 i++ 执行速度比 i + 1 快？
**答案-1:** 表达式 i++ 需要 INR 等单条机器指令来执行增量操作，而 i + 1 需要更多指令来执行该操作。

**问题-2:** 是写 if(！ [strcmp(s1，s2)](https://www.geeksforgeeks.org/strcmp-in-c-cpp/) )好风格？
**回答-2:** 不，这不是好风格因为如果(！strcmp(s1，s2))调用未定义的行为，因此可能会令人困惑。
 **问题-3:**C 语言中代码布局最好的风格是什么？
**答案-3:** 主张缩进的体系有很多，但都有相同的基本缺陷。当实际的代码逻辑不遵循缩进时，它们会误导读者。最好完全避免缩进，这样读者就不会被误导。

**问题-4:**[转](https://www.geeksforgeeks.org/goto-statement-in-c-cpp/)是好事还是坏事？
**回答-4:** 我们应该避免使用 goto 语句，只在必要时使用。

**问题-5:** 为什么[预增量](https://www.geeksforgeeks.org/g-fact-40/)算子比后增量算子快？
**答案-5:** 评价任何表情都是从左到右。预增量运算符比后增量运算符更快，因为它不保存下一条指令的当前值，而后增量运算符需要保存当前值，以便在执行当前指令后递增。

**问题-6:**printf(" % d ")的输出是多少？
**答案-6:** printf("%d "，I)表示编译器会打印 I 的值，因为%d 之后什么都没有，所以编译器会在输出窗口显示垃圾值。