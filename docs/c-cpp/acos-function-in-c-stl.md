# c++ STL 中的 acos()函数

> 原文:[https://www.geeksforgeeks.org/acos-function-in-c-stl/](https://www.geeksforgeeks.org/acos-function-in-c-stl/)

**acos()** 是 C++ STL 中的一个内置函数，和数学中余弦的倒数一样。acos()函数返回的值在[0，？]那是弧度的角度。

**语法:**

```cpp
acos(data_type x)
```

**参数:**该函数接受一个强制参数 x，该参数指定应该计算余弦倒数的值。x 必须在[-1，1]的范围内，才能将有效输出作为[0，？]，否则 acos(x)函数返回 NaN(不是数字)。参数 x 可以是双精度、浮点或长双精度数据类型。

**Return :** 函数以弧度为单位返回[0，？].它是逆时针角度，以弧度为单位。

**程序 1:**

## C++

```cpp
// C++ program to demonstrate
// the acos() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double x = 1.0;

    // Function call to calculate acos(x) value
    double result = acos(x);

    cout << "acos(1.0) = " << result <<
                               " radians" << endl;
    cout << "acos(1.0) = " << result * 180 / 3.141592
         << " degrees" << endl;

    return 0;
}
```

**Output**

```cpp
acos(1.0) = 0 radians
acos(1.0) = 0 degrees
```

**程序 2:**

## C++

```cpp
// C++ program to demonstrate
// the acos() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double result;
    int x = -1;

    // Function call to calculate acos(x) value
    result = acos(x);

    cout << "acos(-1) = " << result
        << " radians" << endl;
    cout << "acos(-1) = " << result * 180 / 3.141592
        << " degrees" << endl;

    return 0;
}
```

**Output**

```cpp
acos(-1) = 3.14159 radians
acos(-1) = 180 degrees
```

**错误和异常:**

*   当字符串或字符作为参数传递时，该函数不返回匹配的错误调用函数。
*   当域外(域[-1，1])数字作为参数传递时，函数返回 nan。

下面的程序说明了上述方法的错误和异常:

**程序 3:**

## C++

```cpp
// C++ program to demonstrate the acos()
// function errors and exceptions
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double result;
    string x = "gfg";
    result = acos(x);

    cout << "acos(x) = " << result
        << " radians" << endl;
    cout << "acos(x) = " << result * 180 / 3.141592
        << " degrees" << endl;

    return 0;
}
```

**输出:**

```cpp
prog.cpp:10:17: error: no matching function for call to 'acos(std::__cxx11::string&)'
  result = acos(x);
```

当参数 x >1 或 x

**程序 4:**

## C++

```cpp
// C++ program to demonstrate the
// acos() function errors and exceptions
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double x = 3.7, result;

    // Function call to calculate acos(x) value
    result = acos(x);

    cout << "acos(3.7) = " << result
        << " radians" << endl;
    cout << "acos(3.7) = " << result * 180 / 3.141592
        << " degrees" << endl;

    return 0;
}
```

**输出:**

```cpp
acos(3.7) = nan radians
acos(3.7) = nan degrees
```