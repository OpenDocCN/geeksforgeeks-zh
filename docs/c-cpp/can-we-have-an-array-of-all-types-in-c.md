# 有哪些数据类型是无法创建数组的？

> 原文:[https://www . geeksforgeeks . org/can-we-有一个全类型数组 in-c/](https://www.geeksforgeeks.org/can-we-have-an-array-of-all-types-in-c/)

在 C 语言中，除了下列类型之外，可以有所有类型的数组。
1)无效。
2)功能。

例如，下面的程序抛出编译器错误

```cpp
int main()
{
    void arr[100];
}

```

输出:

```cpp
error: declaration of 'arr' as array of voids 
```

但是我们可以有空指针和函数指针的数组。下面的程序运行良好。

```cpp
int main()
{
    void *arr[100];
}

```

数组函数指针详见[函数指针示例](https://www.geeksforgeeks.org/function-pointer-in-c/)。

本文由**湿婆**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论