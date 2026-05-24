# 标准::数值限制::C++ 中的数字，示例

> 原文: [https://www.geeksforgeeks.org/stdnumeric_limitsdigits-in-c-with-example/](https://www.geeksforgeeks.org/stdnumeric_limitsdigits-in-c-with-example/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中的 `std::numeric_limits<T>::digits` 功能存在于 `<limits>` 头文件中。`std::numeric_limits<T>::digits` 函数用于在不损失精度的情况下，查找数据类型可以表示的基数位数。

## 头文件

```cpp
#include<limits>
```

## 模板

```cpp
static const int digits;
static constexpr int digits;
```

## 语法

```cpp
std::numeric_limits<T>::digits
```

## 参数

函数 `std::numeric_limits<T>::digits` 不接受任何参数。

## 返回值

函数 `std::numeric_limits<T>::digits` 返回该类型可以表示的基数位数而不损失精度。

下面是用 C++ 演示 `std::numeric_limits<T>::digits` 的程序:

## 程序

```cpp
// C++ program to illustrate
// std::numeric_limits<T>::digits
#include <bits/stdc++.h>
#include <limits>
using namespace std;

// Driver Code
int main()
{
    // Print the numeric digit for
    // the various data type
    cout << "For int: "
         << numeric_limits<int>::digits
         << endl;

    cout << "For float: "
         << numeric_limits<float>::digits
         << endl;

    cout << "For double: "
         << numeric_limits<double>::digits
         << endl;

    cout << "For long double: "
         << numeric_limits<long double>::digits
         << endl;

    return 0;
}
```

## 输出

```cpp
For int: 31
For float: 24
For double: 53
For long double: 64
```

## 参考

[https://en.cppreference.com/w/cpp/types/numeric_limits/digits](https://en.cppreference.com/w/cpp/types/numeric_limits/digits)