# char 数组的单引号和双引号声明有什么区别？

> 原文:[https://www.geeksforgeeks.org/g-fact/](https://www.geeksforgeeks.org/g-fact/)

在 C/C++ 中，当字符数组用双引号字符串初始化且未指定数组大小时，编译器会自动为字符串结束符“\0”分配一个额外的空间。例如，以下程序打印 6 作为输出。

```cpp
#include<stdio.h>
int main()
{
  // size of arr[] is 6 as it is '\0' terminated 
  char arr[] = "geeks";

  printf("%lu", sizeof(arr));

  return 0;
}
```

输出:

```cpp
6
```

如果数组大小在上面的程序中被指定为 5，那么程序在没有任何警告/错误的情况下工作，并且在 C 中打印 5，但是在 C++ 中导致编译错误。

```cpp
// Works in C, but compilation error in C++
#include<stdio.h>
int main()
{
  // arr[] is not terminated with '\0'
  // and its size is 5
  char arr[5] = "geeks"; 

  printf("%lu", sizeof(arr));

  return 0;
}
```

输出:

```cpp
5
```

当用逗号分隔的字符列表初始化字符数组并且未指定数组大小时，编译器不会为字符串结束符“\0”创建额外的空间。例如，下面的程序打印 5。

```cpp
#include<stdio.h>
int main()
{
  // arr[] is not terminated with '\0' 
  // and its size is 5 
  char arr[]= {'g', 'e', 'e', 'k', 's'}; 

  printf("%lu", sizeof(arr));

  return 0;
}
```

输出:

```cpp
5
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。