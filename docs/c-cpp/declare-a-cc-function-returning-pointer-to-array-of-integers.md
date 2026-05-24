# 声明一个 C/C++ 函数返回指针到整数指针数组

> 原文:[https://www . geesforgeks . org/declare-a-cc-function-returning-指针指向整数数组/](https://www.geeksforgeeks.org/declare-a-cc-function-returning-pointer-to-array-of-integers/)

声明“一个参数为 *int** 的函数，该函数返回指向 4 个整数指针数组的指针”。

乍一看，它可能看起来很复杂，我们可以用一系列分解的语句来声明所需的函数。

1.我们需要一个带参数的函数 *int ** ，

```cpp
function(int *)
```

2.参数为 *int ** 的函数，返回指针

```cpp
(*function(int *))
```

3.带有参数 *int ** 的函数，返回指针到 4 的数组

```cpp
(*function(int *))[4]
```

4.带有参数 *int ** 的函数，返回指向 4 个整数指针数组

```cpp
int *(*function(int *))[4];
```

的指针

我们如何确保上述声明是正确的？以下程序可以交叉检查我们的申报，

```cpp
#include<stdio.h>

// Symbolic size
#define SIZE_OF_ARRAY (4)

// pointer to array of (SIZE_OF_ARRAY) integers
typedef int *(*p_array_t)[SIZE_OF_ARRAY];

// Declaration : compiler should throw error
// if not matched with definition
int *(*function(int *arg))[4];

// Definition  : 'function' returning pointer to an
// array of integer pointers
p_array_t function(int *arg)
{
   // array of integer pointers
   static int *arr[SIZE_OF_ARRAY] = {NULL};

   // return this
   p_array_t pRet = &arr;

   return pRet;
}

int main()
{          
}
```

宏 SIZE_OF_ARRAY 用于数组大小的符号表示。 *p_array_t* 类型定义为“指向 4 个整数的数组的指针”。如果我们的声明是错误的，程序会在“*函数*的定义中抛出一个错误。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。