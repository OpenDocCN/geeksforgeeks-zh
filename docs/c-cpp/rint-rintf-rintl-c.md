# rint()、rinf()、rint()在 C++

中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/rint-rint-rint-c/

rint()用于将浮点参数舍入为整数值(浮点格式)。您也可以使用函数 **fesetround()** 来确定当前的舍入模式，根据该函数，rint 函数返回舍入的整数值。

```cpp
Syntax
double rint(double x);
float rint(float x);
long double rint(long double x);

Header file :  cmath
Parameters :  The rint() function takes a single 
argument value to round.

Returns :   By default, the rounding direction is set to 
'to-nearest' otherwise the rint() function rounds the argument 
to an integral value, using the rounding direction 
specified by fegetround() and returns the value.

```

**异常或错误**
1。如果函数的结果超出返回类型的范围，可能会出现域错误。
2。如果参数为 0，则不加修改地返回。
3。如果参数为*无穷大*，则不加修改地返回。

**示例:**

```cpp
Input : 3.3
Output : 3

Input : 3.5
Output : 4

Input : 3.7
Output : 4

```

```cpp
// CPP program to illustrate rint()
#include <cmath>
#include <iostream>
using namespace std;
// Driver Program
int main()
{
    double a, b, x = 3.3, y = 3.7;

    // Saves the rounded value to a variable
    a = rint(x);
    b = rint(y);

    // Prints the rounded value
    cout << a << endl;

    cout << b;
    return 0;
}
```

输出:

```cpp
3
4

```

**fese trond()功能**

默认情况下，舍入方向设置为最接近的整数。但是使用 fesetround()函数，我们可以确定我们选择的方向。
**语法:**

```cpp
fesetround(FE_DOWNWARD)
fesetround(FE_UPWARD)
Header file : cfenv
```

**示例:**

*   如果 rint()函数与参数 3.7 一起使用，并且还使用了 fesetround(FE _ download)，则输出将是 3
*   如果 rint()函数与参数 3.3 一起使用，并且还使用了 FeS etround(FE _ UPDATE)，则输出将是 4

```cpp
// CPP program to illustrate rint()
// with fesetround() function
#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;
// Driver Program
int main()
{
    double x = 3.7, y = 3.3, result;

    // setting rounding direction to DOWNWARD
    fesetround(FE_DOWNWARD);

    result = rint(x);
    cout << result << endl;

    // setting rounding direction to UPWARD
    fesetround(FE_UPWARD);

    result = rint(y);
    cout << result << endl;

    return 0;
}
```

输出:

```cpp
3
4

```

**rintf()功能**

rintf()函数与 rint 函数相同。唯一的区别是函数的参数和返回类型是浮点类型。附加在“rintf”后面的“f”字符代表 float，它表示函数的参数类型和返回类型。

```cpp
Syntax :
float rintf(float x);

```

这里，变量被赋予浮点类型，否则*类型不匹配*错误发生。

```cpp
// CPP program to illustrate rinft()
#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;
// Driver Program
int main()
{
    float x = 3.76542, y = 3.37562, result;
    // setting rounding direction to DOWNWARD
    fesetround(FE_DOWNWARD);

    result = rintf(x);
    cout << result << endl;

    // setting rounding direction to UPWARD
    fesetround(FE_UPWARD);

    result = rintf(y);
    cout << result << endl;

    return 0;
}
```

输出:

```cpp
3
4

```

**rintl()功能**

rintl()函数与 rint 函数相同。唯一的区别是函数的参数和返回类型是长双精度类型。“rintl”后面的“l”字符代表长双精度，它表示函数的参数类型和返回类型。

```cpp
Syntax : 
long double rintl(long double x);

```

这里，变量被赋予长双类型，否则*类型不匹配*错误发生。

```cpp
// CPP program to illustrate rinfl()

#include <cfenv>
#include <cmath>
#include <iostream>
using namespace std;

// Driver Program
int main()
{
    long double x = 3.765426764, y = 3.37562657, result;

    // setting rounding direction to DOWNWARD
    fesetround(FE_DOWNWARD);

    result = rintl(x);
    cout << result << endl;

    // setting rounding direction to UPWARD
    fesetround(FE_UPWARD);

    result = rintl(y);
    cout << result << endl;

    return 0;
}
```

输出:

```cpp
3
4

```