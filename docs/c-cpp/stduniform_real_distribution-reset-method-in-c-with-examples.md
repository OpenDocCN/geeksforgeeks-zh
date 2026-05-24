# STD::uniform _ real _ distribution reset()方法用 C++ 举例

> 原文:[https://www . geesforgeks . org/stduniform _ real _ distribution-reset-method-in-c-with-examples/](https://www.geeksforgeeks.org/stduniform_real_distribution-reset-method-in-c-with-examples/)

C++ 中**均匀实分布类**的 **reset()** 方法用来重置这个均匀实分布。

**语法:**

```cpp
void reset();

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法不返回任何东西。

**例:**

```cpp
// C++ code to demonstrate
// the working of reset() function

#include <iostream>

// for uniform_real_distribution function
#include <random>

using namespace std;

int main()
{
    double a = 10, b = 20.5;

    default_random_engine generator;

    // Initializing of uniform_real_distribution class
    uniform_real_distribution<double> distribution(a, b);

    cout << "Next value in uniform_int_distribution: "
         << distribution(generator) << endl;
    cout << "Next value in uniform_int_distribution: "
         << distribution(generator) << endl;
    cout << "Next value in uniform_int_distribution: "
         << distribution(generator) << endl;

    // Using reset()
    distribution.reset();
    cout << endl
         << "uniform_int_distribution has been reset."
         << endl
         << endl;

    // Now the next value won't be in the previous progression
    // and will be another progression
    cout << "Now next value in uniform_int_distribution: "
         << distribution(generator) << endl;

    return 0;
}
```

**输出:**

```cpp
Next value in uniform_int_distribution: 11.3811
Next value in uniform_int_distribution: 14.8158
Next value in uniform_int_distribution: 12.2991

uniform_int_distribution has been reset.

Now next value in uniform_int_distribution: 17.1281

```

**参考:**T2【http://www . cplusplus . com/Reference/random/uniform _ real _ distribution/reset/