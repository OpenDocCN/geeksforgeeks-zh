# STD::uniform _ int _ distribution reset()方法用 C++ 举例

> 原文:[https://www . geesforgeks . org/stduniform _ int _ distribution-reset-method-in-c-with-examples/](https://www.geeksforgeeks.org/stduniform_int_distribution-reset-method-in-c-with-examples/)

C++ 中 **uniform_int_distribution 类**的 **reset()** 方法用于重置这个 uniform_int_distribution。

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

// for uniform_int_distribution function
#include <random>

using namespace std;

int main()
{
    int a = 10, b = 100;

    default_random_engine generator;

    // Initializing of uniform_int_distribution class
    uniform_int_distribution<int> distribution(a, b);

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
Next value in uniform_int_distribution: 10
Next value in uniform_int_distribution: 21
Next value in uniform_int_distribution: 78

uniform_int_distribution has been reset.

Now next value in uniform_int_distribution: 51

```

**参考:**T2【https://en . cppreference . com/w/CPP/numeric/random/uniform _ int _ distribution/reset