# C |动态内存分配|问题 1

> 原文:[https://www . geesforgeks . org/c-dynamic-memory-allocation-question-1/](https://www.geeksforgeeks.org/c-dynamic-memory-allocation-question-1/)

以下配对的最合适匹配(GATE CS 2000)

```cpp
X: m=malloc(5); m= NULL;        1: using dangling pointers
Y: free(n); n->value=5;         2: using uninitialized pointers
Z: char *p; *p = ’a’;           3\. lost memory is:
```

**(A)**X—1Y—3 Z-2
**(B)**(X—2Y—1 Z-3
**(C)**X—3Y—2 Z-1

**(D)**X—3Y—1 Z-2

**答案:** **(D)**

**解释:** X - >一个指针被赋值为 NULL 而没有释放内存所以内存泄漏的一个明显例子
Y - >试图在释放它之后检索值所以悬空指针。
Z - >使用未初始化的指针

[本题测验](https://www.geeksforgeeks.org/quiz-corner-gq/)