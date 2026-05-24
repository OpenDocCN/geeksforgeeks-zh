# 理解 C++ 中的 null ptr

> 原文:[https://www.geeksforgeeks.org/understanding-nullptr-c/](https://www.geeksforgeeks.org/understanding-nullptr-c/)

考虑以下显示空值问题的 C++ 程序(需要空值)

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate problem with NULL
#include <bits/stdc++.h>
using namespace std;

// function with integer argument
void fun(int N)   { cout << "fun(int)"; return;}

// Overloaded function with char pointer argument
void fun(char* s)  { cout << "fun(char *)"; return;}

int main()
{
    // Ideally, it should have called fun(char *),
    // but it causes compiler error.
    fun(NULL); 
}
```

输出:

```cpp
16:13: error: call of overloaded 'fun(NULL)' is ambiguous
     fun(NULL);
```

**以上程序有什么问题？**
空值通常定义为(void *)0，允许将空值转换为整数类型。所以函数调用 fun(NULL)变得模棱两可。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// This program compiles (may produce warning)
#include<stdio.h>
int main()
{
   int x = NULL;
}
```

**nullptr 如何解决问题？**
在上面的程序中，如果我们用 nullptr 替换 NULL，我们得到的输出是“fun(char *)”。
nullptr 是一个关键字，可以在所有需要 NULL 的地方使用。像 NULL 一样，nullptr 是隐式可转换的，可以与任何指针类型相比较。**与 NULL 不同，它不是隐式可转换的，也不能与积分类型**相比较。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// This program does NOT compile
#include<stdio.h>
int main()
{
   int x = nullptr;
}
```

输出:

```cpp
Compiler Error
```

顺便说一下， **nullptr 可转换为 bool。**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// This program compiles
#include<iostream>
using namespace std;

int main()
{
   int *ptr = nullptr;

   // Below line compiles
   if (ptr) { cout << "true"; }   
   else { cout << "false"; }   
}
```

输出:

```cpp
false
```

当我们比较两个简单的指针时，有一些不确定的事情，但是 nullptr_t 类型的两个值之间的比较被指定为，< =和>的比较=返回真，而<和>的比较返回假，并且通过==和将任何指针类型与 nullptr 进行比较！=如果分别为 null 或非 null，则返回 true 或 false。

## C

```cpp
// C++ program to show comparisons with nullptr
#include <bits/stdc++.h>
using namespace std;

// Driver program to test behavior of nullptr
int main()
{
    // creating two variables of nullptr_t type
    // i.e., with value equal to nullptr
    nullptr_t np1, np2;

    // <= and >= comparison always return true
    if (np1 >= np2)
        cout << "can compare" << endl;
    else
        cout << "can not compare" << endl;

    // Initialize a pointer with value equal to np1
    char *x = np1;  // same as x = nullptr (or x = NULL
                    // will also work)
    if (x == nullptr)
        cout << "x is null" << endl;
    else
        cout << "x is not null" << endl;

    return 0;
}
```

输出:

```cpp
can compare
x is null
```

本文由乌卡什·特里维迪供稿。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息