# c++ 中的 fesetround()和 fegetround()及其应用

> 原文:[https://www . geeksforgeeks . org/fese trond-fegetround-c-application/](https://www.geeksforgeeks.org/fesetround-fegetround-c-application/)

**fese trond()**

它设置指定的浮点舍入方向或“当前舍入方向”，这将是浮点舍入宏之一。
在 C++ 中与 rint()、nearbyint()等舍入函数配合使用。

```cpp
Syntax:
int fesetround( int round );
where round can be FE_TONEAREST,
FE_DOWNWARD, FE_UPWARD, FE_TOWARDZERO
Header File : cfenv
Return : The fesetround() function returns 
0 on success and the rounding direction is applied to the required number.

```

**错误和异常:**函数只取 FE _ TONEAREST、FE _ DOWNWARD、FE _ upload、FE_TOWARDZERO 作为参数，否则返回错误。

**应用:** fesetround()函数可以和数学头的 rint()、nearbyint()等舍入函数一起使用，应用“当前舍入方向”

```cpp
// C program to illustrate
// fesetround() function with rint() function

#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;
// Driver Program
int main()
{
    double x = 3.7, result;
    // setting rounding direction to the nearest integer
    fesetround(FE_TONEAREST);
    result = rint(x);
    cout << result << endl;

    // setting rounding direction towards zero
    fesetround(FE_TOWARDZERO);
    result = rint(x);
    cout << result << endl;

    // setting rounding direction to DOWNWARD
    fesetround(FE_DOWNWARD);
    result = rint(x);
    cout << result << endl;

    // setting rounding direction to UPWARD
    fesetround(FE_UPWARD);
    result = rint(x);
    cout << result << endl;

    return 0;
}
```

输出:

```cpp
4
3
3
4
```

炼狱()

用于获取当前舍入方向对应的浮点舍入宏的值。它与 rint()，nearbyint()和 C++ 中的其他舍入函数一起使用。

```cpp
Syntax : 
int fegetround();
No parameter
Header File : cfenv
Return : The fegetround() function returns the
floating point rounding macro describing the current 
rounding direction.
Rounding Macros:
1.FE_DOWNWARD
2.FE_TONEAREST
3.FE_TOWARDZERO
4.FE_UPWARD

```

**错误和异常:**

1.  该函数不接受任何参数，因此如果传递参数，将返回一个错误
2.  如果没有使用 fesetround()指定舍入方向，它将返回宏 FE _ TONEAREST

**应用:** fegetround()函数可以和数学头的 rint()、nearbyint()等舍入函数一起使用，利用宏得到“当前舍入方向”。

在这个程序中，我们将检查并打印 fegetround()函数返回的宏。

```cpp
// C program to illustrate
// fegetround() function with
// rint() function using switch case

#include <cfenv>
#include <cmath>
#include <iostream>
#pragma STDC FENV_ACCESS ON
using namespace std;

void direction()
{
    switch (fegetround()) {
    case FE_TONEAREST:
        cout << "FE_TONEAREST";
        break;
    case FE_DOWNWARD:
        cout << "FE_DOWNWARD";
        break;
    case FE_UPWARD:
        cout << "FE_UPWARD";
        break;
    case FE_TOWARDZERO:
        cout << "FE_TOWARDZERO";
        break;
    default:
        cout << "unknown";
    };
    cout << endl;
}
// Driver Program
int main()
{
    double x = 3.7;
    fesetround(FE_UPWARD);
    rint(x);
    direction();

    fesetround(FE_DOWNWARD);
    rint(x);
    direction();

    fesetround(FE_TOWARDZERO);
    rint(x);
    direction();

    fesetround(FE_TONEAREST);
    rint(x);
    direction();

    return 0;
}
```

输出:

```cpp
FE_UPWARD
FE_DOWNWARD
FE_TOWARDZERO
FE_TONEAREST
```