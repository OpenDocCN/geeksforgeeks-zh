# C++ 中的 `logical_and`

> 原文: [https://www.geeksforgeeks.org/logical_and-in-c/](https://www.geeksforgeeks.org/logical_and-in-c/)

C++ 中的 `logical_and` 是一个二元函数对象类，它返回其两个参数之间的逻辑“与”运算的结果（由运算符 `&&` 返回）。

## 语法

```cpp
template<class T> struct logical_and : binary_function<T,T,bool>
{
  T operator() (const T& a, const T& b) const {return a&&b;}
};
```

## 参数

*   `T`：参数的类型和函数调用的返回类型。

## 成员类型

*   `a`：成员运算符 `()` 中第一个参数的类型。
*   `b`：成员运算符 `()` 中第二个参数的类型。
*   `result_type`：成员运算符 `()` 返回的类型。

以下是使用 `std::transform()` 实现 `logical_and` 的程序：

## 示例代码

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    bool z[] = { true, false, true, false, true };
    bool y[] = { true, true, false, false, true };
    int n = 5;
    bool result[n];

    // using transform to
    // perform logical_AND on two array
    transform(z, z + n, y, result,
              logical_and<bool>());

    cout << "Logical AND:\n";
    for (int i = 0; i < n; i++)
        cout << z[i] << " AND " << y[i]
             << " = " << result[i] << "\n";
    return 0;
}
```

### 输出

```cpp
Logical AND:
1 AND 1 = 1
0 AND 1 = 0
1 AND 0 = 0
0 AND 0 = 0
1 AND 1 = 1
```