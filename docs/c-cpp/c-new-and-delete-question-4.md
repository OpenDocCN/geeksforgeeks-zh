# C++ |新增和删除|问题 4

> 原文:[https://www.geeksforgeeks.org/c-new-and-delete-question-4/](https://www.geeksforgeeks.org/c-new-and-delete-question-4/)

当删除用于空指针时会发生什么？

```cpp
int *ptr = NULL;
delete ptr; 
```

**(A)** 编译器错误
**(B)** 运行时崩溃
**(C)** 无影响

**回答:****(C)**

**说明:**删除空指针没有影响，所以在调用 delete 之前没有必要检查空指针。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)