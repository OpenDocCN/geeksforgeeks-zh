# C++ |新增和删除|问题 5

> 原文:[https://www.geeksforgeeks.org/c-new-and-delete-question-5/](https://www.geeksforgeeks.org/c-new-and-delete-question-5/)

为一个指针调用 delete 两次可以吗？

```cpp
#include<iostream>
using namespace std;

int main()
{
    int *ptr = new int;
    delete ptr;
    delete ptr;
    return 0;
}
```

**(A)** 是
**(B)** 否

**回答:** **(B)**

**说明:**在指针上两次调用 delete 是未定义行为。

任何事情都有可能发生，程序可能崩溃或者什么都不会产生。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)