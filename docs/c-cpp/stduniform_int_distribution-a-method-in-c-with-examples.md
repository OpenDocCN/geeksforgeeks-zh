# STD::uniform _ int _ distribution a()方法用 C++ 举例

> 原文:[https://www . geesforgeks . org/stduniform _ int _ distribution-a-method-in-c-with-examples/](https://www.geeksforgeeks.org/stduniform_int_distribution-a-method-in-c-with-examples/)

用 C++ 中**均匀 int 分布类**的 **a()** 方法得到这个均匀 int 分布的下界。如果没有下限，则此方法返回 0。

**语法:**

```cpp
result_type a() const;

```

**参数:**该方法不接受任何参数。

**返回值:**此方法返回分布中的‘a’参数，该参数是此 uniform_int_distribution 中可能生成的值的下限或最小值。其默认值为 0。

**例:**

```cpp
// C++ code to demonstrate
// the working of a() function

#include <iostream>

// for uniform_int_distribution function
#include <random>

using namespace std;

int main()
{
    int a = 10, b = 100;

    // Initializing of uniform_int_distribution class
    uniform_int_distribution<int> distribution(a, b);

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

**参考:**[https://en . cppreference . com/w/CPP/numeric/random/uniform _ int _ distribution/params](https://en.cppreference.com/w/cpp/numeric/random/uniform_int_distribution/params)