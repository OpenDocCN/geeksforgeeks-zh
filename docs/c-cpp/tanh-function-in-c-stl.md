# c++ STL 中的 tanh()函数

> 原文:[https://www.geeksforgeeks.org/tanh-function-in-c-stl/](https://www.geeksforgeeks.org/tanh-function-in-c-stl/)

**tanh()** 是 C++ STL 中的一个内置函数，它返回以弧度给出的角度的双曲正切值。

**语法:**

```cpp
tanh(data_type x)

```

**参数:**函数接受一个强制参数 *x* ，以弧度为单位指定双曲角。参数可以是双精度、浮点或长双精度数据类型。

**返回值:**函数返回自变量的双曲正切值。

下面的程序说明了上述方法:

**程序 1:**

```cpp
// CPP program to demonstrate the
// tanh() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double x = 4.1, result;

    result = tanh(x);
    cout << "tanh(4.1) = " << result << endl;

    // x in Degrees
    double xDegrees = 90;
    x = xDegrees * 3.14159 / 180;

    result = tanh(x);
    cout << "tanh(90 degrees) = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
tanh(4.1) = 0.999451
tanh(90 degrees) = 0.917152

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// tanh() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int x = -4;
    double result;

    result = tanh(x);
    cout << "tanh(-4) = " << result << endl;

    // x in Degrees
    double xDegrees = 90;
    x = xDegrees * 3.14159 / 180;

    result = tanh(x);
    cout << "tanh(90 degrees) = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
tanh(-4) = -0.999329
tanh(90 degrees) = 0.761594

```

**错误和异常:**当字符串或字符作为参数传递时，该函数不返回匹配的错误调用函数。

**程序 3:**

```cpp
// CPP program to demonstrate the tanh()
// function when a string is passed as argument 
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string x = "gfg";
    double result;

    result = tanh(x);
    cout << "tanh(x) = " << result << endl;

    return 0;
}
```

**输出:**

```cpp
prog.cpp:14:20: error: no matching function for call to 'tanh(std::__cxx11::string&)'
result = tanh(x);

```