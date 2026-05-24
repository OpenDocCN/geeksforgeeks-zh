# STD::uniform _ real _ distribution a()方法用 C++ 举例

> 原文:[https://www . geesforgeks . org/stduniform _ real _ distribution-a-in-c-method-in-with-examples/](https://www.geeksforgeeks.org/stduniform_real_distribution-a-method-in-c-with-examples/)

用 C++ 中**均匀实分布类**的 **a()** 方法得到这个均匀实分布的下界。

**语法:**

```cpp
result_type a() const;

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回分布中的‘a’参数，该参数是这个 uniform_real_distribution 中可能生成的值的下限或最小值。

**例:**

```cpp
// C++ code to demonstrate
// the working of a() function

#include <iostream>

// for uniform_real_distribution function
#include <random>

using namespace std;

int main()
{
    double a = 10, b = 20.5;

    // Initializing of uniform_real_distribution class
    uniform_real_distribution<double> distribution(a, b);

    // Using a()
    cout << "Lower Bound: "
         << distribution.a() << endl;

    return 0;
}
```

**输出:**

```cpp
Lower Bound: 10

```

**参考:**T2【http://www . cplusplus . com/Reference/random/uniform _ real _ distribution/a/