# 引用可以引用 C++ 中的无效位置吗？

> 原文:[https://www.geeksforgeeks.org/g-fact-25/](https://www.geeksforgeeks.org/g-fact-25/)

在 C++ 中，[引用变量](http://en.wikipedia.org/wiki/Reference_%28C%2B%2B%29)比指针更安全，因为引用变量必须被初始化，并且一旦被初始化就不能被更改为引用其他东西。但是也有例外，我们可以有无效的引用。

1)引用未初始化指针处的值。

```cpp
int *ptr;
int &ref = *ptr;  // Reference to value at some random memory location
```

2)返回对局部变量的引用。

```cpp
int& fun()
{
   int a = 10;
   return a;
}
```

一旦 fun()返回，堆栈帧上分配给它的空间将被收回。所以对局部变量的引用是无效的。

如果你在上面的 GFact 中发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。