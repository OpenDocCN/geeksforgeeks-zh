# C 和 C++ 中比较运算的结果

> 原文:[https://www . geeksforgeeks . org/c-in-c-and-c 操作比较结果/](https://www.geeksforgeeks.org/results-of-comparison-operations-in-c-and-c/)

在 C 语言中，比较运算结果的数据类型是 int。例如，请参见以下程序。

```cpp
#include<stdio.h>
int main()
{
    int x = 10, y = 10;
    printf("%d \n", sizeof(x == y));
    printf("%d \n", sizeof(x < y));
    return 0;
}
```

输出:

```cpp
4
4
```

而在 C++ 中，比较运算的结果类型是 bool。例如，请参见以下程序。

```cpp
#include<iostream>
using namespace std;

int main()
{
    int x = 10, y = 10;
    cout << sizeof(x == y) << endl;
    cout << sizeof(x < y);
    return 0;
}
```

输出:

```cpp
1
1
```

本文由 **Rajat** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论