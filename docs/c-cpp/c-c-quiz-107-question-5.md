# C 小测验–107 |问题 5

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-107-question-5/](https://www.geeksforgeeks.org/c-c-quiz-107-question-5/)

对于 C 语言中函数的以下声明，选择最佳语句

```cpp
int [] fun(void (*fptr)(int *));
```

**(A)** 会导致编译错误。
**(二)**无编译错误。fun 是一个以函数指针 fptr 为参数，返回 int 数组的函数。
**(C)** 无编译错误。fun 是一个以函数指针 fptr 为参数，返回 int 数组的函数。另外，fptr 是一个函数指针，它以 int 指针为参数，返回 void。
**(D)** 无编译错误。fun 是一个以函数指针 fptr 为参数，返回 int 数组的函数。int 的数组取决于 fun 的主体，即返回什么大小的数组。另外，fptr 是一个函数指针，它以 int 指针为参数，返回 void。

**回答:****(A)**

**说明:**按照 C 标准，函数不能有显式数组作为返回类型。这就是为什么上面会导致编译错误。如果我们需要一个数组作为函数调用的输出，有间接的方法。例如，可以通过 *return* 语句通过函数返回指针，同时通过其他方式提供数组的大小。或者，可以为此使用函数参数。

[本题小考](https://www.geeksforgeeks.org/c-quiz-107-gq/)