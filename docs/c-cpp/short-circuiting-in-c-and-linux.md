# c++ 和 Linux 中的短路

> 原文:[https://www . geesforgeks . org/c 与 linux 短路/](https://www.geeksforgeeks.org/short-circuiting-in-c-and-linux/)

短路是编译器的优化步骤之一，在这个步骤中，在表达式求值期间避免了不必要的计算。表达式从左到右计算。在某些情况下，只需计算表达式的一部分，就可以计算出表达式的值。

**<u>C++ 中的短路</u>**
在 c++ 中，短路发生在计算“&&”“(AND)和“| |”(OR)逻辑运算符时。在评估“& &”运算符时，如果“& &”的左侧给出 false，则表达式将始终产生 false，而不管“& &”右侧的值如何，因此检查“& &”的右侧没有意义。因此，在这种情况下，编译器避免了对右侧的评估。同样，在逻辑“或”||”运算的情况下，当左侧给出“真”时，表达式的结果将始终为真，而与右侧的值无关。

**使用 AND( & &)和 OR(||)逻辑运算符短路。**

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Short circuiting
    // logical "||"(OR)
    int a = 1, b = 1, c = 1;

    // a and b are equal
    if (a == b || c++) {
        cout << "Value of 'c' will"
             << "  not increment due"
             << " to short-circuit"
             << endl;
    }
    else {
        cout << "Value of 'c' "
             << " is incremented as there"
             << " is no short-circuit"
             << endl;
    }

    // Short circuiting
    // logical "&&"(OR)

    if (a == b && c++) {
        cout << "Value of 'c' will"
             << " increment as there"
             << " is no short circuit"
             << endl;
    }
    else {
        cout << "Value of 'c' will"
             << " not increment due to short circuit"
             << endl;
    }
}
```

**Output:**

```cpp
Value of 'c' will  not increment due to short-circuit
Value of 'c' will increment as there is no short circuit
```