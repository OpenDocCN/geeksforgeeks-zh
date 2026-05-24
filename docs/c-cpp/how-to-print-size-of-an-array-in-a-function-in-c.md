# 如何在 C++ 中打印数组参数的大小？

> 原文:[https://www . geesforgeks . org/如何打印 c 中函数数组大小/](https://www.geeksforgeeks.org/how-to-print-size-of-an-array-in-a-function-in-c/)

如何计算函数中数组参数的大小？
考虑下面的 C++ 程序:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A C++ program to show that it is wrong to
// compute size of an array parameter in a function
#include <iostream>
using namespace std;

void findSize(int arr[])
{
    cout << sizeof(arr) << endl;
}

int main()
{
    int a[10];
    cout << sizeof(a) << " ";
    findSize(a);
    return 0;
}
```

输出:

```cpp
40 8
```

上面的输出是针对整数大小为 4 字节，指针大小为 8 字节的机器。主打印 40 中的 **cout** 语句和 findSize 打印 8 中的 **cout** 语句。原因是，数组总是在函数中传递指针，即 findSize(int arr[])和 findSize(int *arr)的意思完全一样。因此，findSize()中的 cout 语句打印指针的大小。详见[本](https://www.geeksforgeeks.org/using-sizof-operator-with-array-paratmeters/)[本](https://www.geeksforgeeks.org/why-c-treats-array-parameters-as-pointers/)。
**如何在函数中找到数组的大小？**
我们可以传递一个‘引用数组’。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A C++ program to show that we can use reference to
// find size of array
#include <iostream>
using namespace std;

void findSize(int (&arr)[10])
{
    cout << sizeof(arr) << endl;
}

int main()
{
    int a[10];
    cout << sizeof(a) << " ";
    findSize(a);
    return 0;
}
```

输出:

```cpp
40 40
```

上面的程序看起来不太好，因为我们有一个数组参数的硬编码大小。我们可以用 C++ 中的[模板](http://geeksquiz.com/templates-cpp/)做得更好。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A C++ program to show that we use template and
// reference to find size of integer array parameter
#include <iostream>
using namespace std;

template <size_t n>
void findSize(int (&arr)[n])
{
    cout << sizeof(int) * n << endl;
}

int main()
{
    int a[10];
    cout << sizeof(a) << " ";
    findSize(a);
    return 0;
}
```

输出:

```cpp
40 40
```

我们也可以做一个通用函数:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A C++ program to show that we use template and
// reference to find size of any type array parameter
#include <iostream>
using namespace std;

template <typename T, size_t n>
void findSize(T (&arr)[n])
{
    cout << sizeof(T) * n << endl;
}

int main()
{
    int a[10];
    cout << sizeof(a) << " ";
    findSize(a);

    float f[20];
    cout << sizeof(f) << " ";
    findSize(f);
    return 0;
}
```

输出:

```cpp
40 40
80 80
```

现在下一步是打印动态分配的数组的大小。这是你的任务！我给你一个提示。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <cstdlib>
using namespace std;

int main()
{
    int *arr = (int*)malloc(sizeof(int) * 20);
    return 0;
}
```

本文由 **Swarupananda Dhua** 供稿，如发现有不正确的地方请写评论，或者想分享更多关于以上讨论话题的信息