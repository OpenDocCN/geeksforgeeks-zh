# C |数组|问题 14

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-8/](https://www.geeksforgeeks.org/c-arrays-question-8/)

关于 C.
**(A)** 中的数组，以下哪一项是正确的对于每一个类型 T，都可以有一个 T 的数组.
**(B)** 对于除了 void 和 function 类型之外的每一个类型 T，都可以有一个 T 的数组.
**(C)** 当一个数组被传递给一个函数时，C 编译器会创建一个数组的副本。
**(D)** 2D 数组以列主形式存储

**回答:****(B)**

**说明:**在 C 语言中，我们不能有空类型和函数类型的数组。

例如，下面的程序抛出编译器错误

```cpp
int main()
{
    void arr[100];
}

```

但是我们可以有空指针和函数指针的数组。下面的程序运行良好。

```cpp
int main()
{
    void *arr[100];
}

```

数组函数指针详见[函数指针示例](https://www.geeksforgeeks.org/function-pointer-in-c/)。

[本题小考](http://quiz.geeksforgeeks.org/c-languag-2/arrays-pointers/)