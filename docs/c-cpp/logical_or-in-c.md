# c++ 中的逻辑 _ or

> 原文:[https://www.geeksforgeeks.org/logical_or-in-c/](https://www.geeksforgeeks.org/logical_or-in-c/)

C++ 中的**logic _ or**是一个二进制函数对象类，它返回其两个参数之间的逻辑“or”运算的结果(由运算符||)返回。

**语法:**

```cpp
template  struct logical_or : binary_function  
{
  T operator() (const T& a, const T& b) const {return a||b;}
};

```

**参数:** (T)参数的类型和函数调用的返回类型。该类型应支持该操作(二元运算符||)。

**成员类型:**

*   **A:** The type of the first parameter in the member operator ()
*   **B:** The type of the second parameter in the member operator ()
*   **Result _ Type:** The type returned by the member operator ()

下面是使用[STD::transform()](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/):

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // First array
    int z[] = { 1, 0, 1, 0 };

    // Second array
    int y[] = { 1, 1, 0, 0 };
    int n = 4;
    // Result array
    int result[n];

    // transform applies logical_or
    // on both the array
    transform(z, z + n, y, 
           result, logical_or<int>());

    cout<< "Logical OR:\n";
    for (int i = 0; i < n; i++)

        // Printing the result array
        cout << z[i] << " OR " << y[i] 
             << " = " << result[i] << "\n";
    return 0;
}
```

**输出:**

```cpp
Logical OR:
1 OR 1 = 1
0 OR 1 = 1
1 OR 0 = 1
0 OR 0 = 0

```

实现**逻辑 _ 和**的程序