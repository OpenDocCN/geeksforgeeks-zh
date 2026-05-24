# 如何从 C/C++ 函数返回局部数组？

> 原文:[https://www . geesforgeks . org/return-local-array-c-function/](https://www.geeksforgeeks.org/return-local-array-c-function/)

考虑下面的 C++ 程序。从函数中返回数组是正确的方法吗？

## C

```cpp
#include <stdio.h>

int* fun()
{
    int arr[100];

    /* Some operations on arr[] */
    arr[0] = 10;
    arr[1] = 20;

    return arr;
}

int main()
{
    int* ptr = fun();
    printf("%d %d", ptr[0], ptr[1]);
    return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int* fun()
{
    int arr[100];

    /* Some operations on arr[] */
    arr[0] = 10;
    arr[1] = 20;

    return arr;
}

int main()
{
    int* ptr = fun();
    cout << ptr[0] << " " << ptr[1];
    return 0;
}
```

**警告:**

```cpp
In function 'int* fun()':
6:8: warning: address of local variable 'arr' returned [-Wreturn-local-addr]
    int arr[100];
        ^

```

**Output:** 

```cpp
10 20

```