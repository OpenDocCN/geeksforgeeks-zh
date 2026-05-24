# c++ STL 中的 cosh()函数

> 原文:[https://www.geeksforgeeks.org/cosh-function-in-c-stl/](https://www.geeksforgeeks.org/cosh-function-in-c-stl/)

**cosh()** 是 C++ STL 中的一个内置函数，它返回以弧度给出的角度的双曲余弦值。

**语法:**

```cpp
cosh(data_type x)

```

**参数:**函数接受一个强制参数 *x* ，以弧度为单位指定双曲角。参数可以是双精度、浮点或长双精度数据类型。

**返回值:**函数返回参数的双曲余弦值。如果结果的幅度太大，无法用返回类型的值来表示，则函数返回 **inf** 。

下面的程序说明了上述方法:

**程序 1:**

```cpp
// CPP program to demonstrate the
// cosh() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double x = 4.1, result;

    result = cosh(x);
    cout << "cosh(4.1) = " << result << endl;

    // x in Degrees
    double xDegrees = 90;
    x = xDegrees * 3.14159 / 180;

    result = cosh(x);
    cout << "cosh(90 degrees) = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
cosh(4.1) = 30.1784
cosh(90 degrees) = 2.50918

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// cosh() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int x = -4;
    double result;

    result = cosh(x);
    cout << "cosh(-4) = " << result << endl;

    // x in Degrees
    double xDegrees = 90;
    x = xDegrees * 3.14159 / 180;

    result = cosh(x);
    cout << "cosh(90 degrees) = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
cosh(-4) = 27.3082
cosh(90 degrees) = 1.54308

```

**错误和异常:**当字符串或字符作为参数传递时，该函数不返回匹配的错误调用函数。

**程序 3:**

```cpp
// CPP program to demonstrate the 
// cosh() function when string passed
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string x = "gfg";
    double result;

    result = cosh(x);
    cout << "cosh("gfg") = " << result << endl;

    return 0;
}
```

**输出:**

```cpp
prog.cpp:14:20: error: no matching function for call to 'cosh(std::__cxx11::string&)'
result = cosh(x);

```

**程序 4:** 当自变量过大时。

```cpp
// CPP program to demonstrate the cosh()
// function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double x = 3000.0, result;

    result = cosh(x);
    cout << "cosh(3000.0) = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
cosh(3000.0) = inf

```