# STD::uniform _ real _ distribution b()方法用 C++ 举例

> 原文:[https://www . geesforgeks . org/stduniform _ real _ distribution-B- method-in-c-with-examples/](https://www.geeksforgeeks.org/stduniform_real_distribution-b-method-in-c-with-examples/)

用 C++ 中**均匀实分布类**的 **b()** 方法得到这个均匀实分布的上界。

**语法:**

```cpp
result_type b() const;

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回分布中的‘b’参数，该参数是这个 uniform_real_distribution 中可能生成值的上限或最大值。

**例:**

```cpp
// C++ code to demonstrate
// the working of b() function

#include <iostream>

// for uniform_real_distribution function
#include <random>

using namespace std;

int main()
{
    double a = 10, b = 20.5;

    // Initializing of uniform_real_distribution class
    uniform_real_distribution<double> distribution(a, b);

    // Using b()
    cout << "Upper Bound: "
         << distribution.b() << endl;

    return 0;
}
```

**输出:**

```cpp
Upper Bound: 20.5

```

**参考:**T2【http://www . cplusplus . com/Reference/random/uniform _ real _ distribution/b/