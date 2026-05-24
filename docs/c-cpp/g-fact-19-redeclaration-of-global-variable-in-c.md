# C 中全局变量的重新声明

> 原文:[https://www . geeksforgeeks . org/g-fact-19-重新声明-全局变量-in-c/](https://www.geeksforgeeks.org/g-fact-19-redeclaration-of-global-variable-in-c/)

考虑以下两个程序:

```cpp
// Program 1
int main()
{
   int x;
   int x = 5;
   printf("%d", x);
   return 0; 
}
```

C 中的输出:

```cpp
redeclaration of ‘x’ with no linkage
```

```cpp
// Program 2
int x;
int x = 5;

int main()
{
   printf("%d", x);
   return 0; 
}
```

C 中的输出:

```cpp
5
```

在 C 语言中，第一个程序编译失败，但第二个程序运行良好。在 C++ 中，两个程序都无法编译。

 **当第一次声明没有初始化变量时，C 允许再次声明一个全局变量。**

下面的程序在两个 C 语言中都失败了，因为全局变量是在第一个声明中初始化的。

```cpp
int x = 5;
int x = 10;

int main()
{
   printf("%d", x);
   return 0;
}
```

输出:

```cpp
 error: redefinition of ‘x’
```

本文由 **Abhay Rathi** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论