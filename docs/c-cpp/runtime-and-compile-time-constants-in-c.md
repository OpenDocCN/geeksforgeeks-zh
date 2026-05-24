# c++ 中的运行时和编译时常数

> 原文:[https://www . geesforgeks . org/runtime-and-compile-time-constants-in-c/](https://www.geeksforgeeks.org/runtime-and-compile-time-constants-in-c/)

**<u>运行时间常数</u> :**

这些常数的各自值只能在运行源代码时知道或计算。运行时常数比编译时常数慢一点，但比编译时常数更灵活。但是，一旦初始化，这些常量的值就不能更改。

下面是运行时常数说明程序:

## c++

```cpp
// C++ program to illustrate
// Run-time Constants
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Input a variable
    double electonmass;
    cin >> electonmass;

    // Define a constant
    // and initialize it at
    // run-time
    const double electon_mass{ electonmass };

    // Known to the compiler
    // at the run-time
    cout << electon_mass << endl;

    return 0;
}
```

**输出:**

```cpp
2.07335e-317

```