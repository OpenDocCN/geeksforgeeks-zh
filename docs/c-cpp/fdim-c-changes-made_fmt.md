# C++ 中的 `fdim()`

> 原文: [https://www.geeksforgeeks.org/fdim-c-changes-made/](https://www.geeksforgeeks.org/fdim-c-changes-made/)

`fdim()` 函数接受两个参数，并返回第一个和第二个参数之间的正差值。

如果 `a > b` 返回 `0`，则该功能返回 `a-b`。其中，`a` 是第一个参数，`b` 是第二个参数。

## 语法

```cpp
double fdim(double a, double b);
float fdim(float a, float b);
```

## 参数

`fdim()` 函数接受两个参数 `a` 和 `b`，其中 `a` 是第一个参数，`b` 是第二个参数。

## 返回

此函数在 `a>b` 时返回 `a-b`，否则返回 `0`。

## 错误

必须提供两个参数，否则将引发错误，例如：`no matching function for call to 'fdim()'`。

## 示例

```cpp
Input : fdim(2.0, 1.0)
Output : 1

Input : fdim(-2.0, 1.0)
Output : 0
```

## 代码 1

```cpp
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    // positive difference for 2.0 and 1.0 is 1
    cout << "fdim of (2.0, 1.0) is " << fdim(2.0, 1.0) << endl;

    // here 1.0<2.0 so the output is 0
    cout << "fdim of (1.0, 2.0) is " << fdim(1.0, 2.0) << endl;

    // here -2.0<-1.0 so the output is 0
    cout << "fdim of (-2.0, -1.0) is " << fdim(-2.0, -1.0) << endl;

    // positive difference for -1.0 and -2.0 is 1
    cout << "fdim of (-1.0, -2.0) is " << fdim(-1.0, -2.0) << endl;

    return 0;
}
```

## 输出

```
fdim of (2.0, 1.0) is 1
fdim of (1.0, 2.0) is 0
fdim of (-2.0, -1.0) is 0
fdim of (-1.0, -2.0) is 1
```

## 代码 2

```cpp
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    // positive difference for 5.0 and 4.0 is 1
    cout << "fdim of (5.0, 4.0) is " << fdim(5.0, 4.0) << endl;

    // here 4.0<5.0 so the output is 0
    cout << "fdim of (4.0, 5.0) is " << fdim(4.0, 5.0) << endl;

    // here -5.0<-4.0 so the output is 0
    cout << "fdim of (-5.0, -4.0) is " << fdim(-5.0, -4.0) << endl;

    // positive difference for 5.0 and 4.0 is 1
    cout << "fdim of (-4.0, -5.0) is " << fdim(-4.0, -5.0) << endl;

    return 0;
}
```

## 输出

```
fdim of (5.0, 4.0) is 1
fdim of (4.0, 5.0) is 0
fdim of (-5.0, -4.0) is 0
fdim of (-4.0, -5.0) is 1
```