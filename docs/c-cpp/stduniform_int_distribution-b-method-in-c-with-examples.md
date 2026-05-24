# STD::uniform _ int _ distribution b()方法用 C++ 举例

> 原文:[https://www . geesforgeks . org/stduniform _ int _ distribution-B- method-in-c-with-examples/](https://www.geeksforgeeks.org/stduniform_int_distribution-b-method-in-c-with-examples/)

用 C++ 中**均匀 int 分布**类的 **b()** 方法得到这个均匀 int 分布的上界。如果没有上限，则该方法返回**标准::数值 _ 限制::最大值()**。

**语法:**

```cpp
result_type b() const;

```

**参数:**该方法不接受任何参数。

**返回值:**此方法返回分布中的‘b’参数，该参数是此 uniform_int_distribution 中可能生成的值的上限或最大值。它的默认值是 std::numeric_limits::max()。

**例:**

```cpp
// C++ code to demonstrate
// the working of b() function

#include <iostream>

// for uniform_int_distribution function
#include <random>

using namespace std;

int main()
{
    int a = 10, b = 100;

    // Initializing of uniform_int_distribution class
    uniform_int_distribution<int> distribution(a, b);

    // Using b()
    cout << "Upper Bound: "
         << distribution.b() << endl;

    return 0;
}
```

**输出:**

```cpp
Upper Bound: 100

```

**参考:**[https://en . cppreference . com/w/CPP/numeric/random/uniform _ int _ distribution/params](https://en.cppreference.com/w/cpp/numeric/random/uniform_int_distribution/params)