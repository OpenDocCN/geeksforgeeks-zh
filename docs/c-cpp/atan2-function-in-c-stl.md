# c++ STL 中的 atan2()函数

> 原文:[https://www.geeksforgeeks.org/atan2-function-in-c-stl/](https://www.geeksforgeeks.org/atan2-function-in-c-stl/)

**atan2()** 是 C++ STL 中的一个内置函数，返回(y/x)的正切倒数，其中 y 是 y 坐标的比例，x 是 x 坐标的比例。数值介于–![\pi ](img/b1e4b020b2fbb98ab91207094bdb1078.png "Rendered by QuickLaTeX.com")和![\pi ](img/b1e4b020b2fbb98ab91207094bdb1078.png "Rendered by QuickLaTeX.com")之间，代表(x，y)点和正 x 轴的角度![\theta ](img/71665d472a66ac434109c1ed1f496e2f.png "Rendered by QuickLaTeX.com")。它是正 X 轴和点(X，y)之间的逆时针角度，以弧度为单位。
**语法:**

```cpp
atan2(data_type y, data_type x)
```

**参数:**该功能接受两个强制参数，描述如下:

*   **y–**该值指定 y 坐标。
*   **x–**该值指定 x 坐标。

参数可以是双精度、浮点或长双精度数据类型。

**返回值:**该函数返回一个介于–![\pi ](img/b1e4b020b2fbb98ab91207094bdb1078.png "Rendered by QuickLaTeX.com")和![\pi ](img/b1e4b020b2fbb98ab91207094bdb1078.png "Rendered by QuickLaTeX.com")之间的数值，代表(x，y)点与正 x 轴的角度![\theta ](img/71665d472a66ac434109c1ed1f496e2f.png "Rendered by QuickLaTeX.com")。它是正 X 轴和点(X，y)之间的逆时针角度，以弧度为单位。
以下程序说明 atan2()功能:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the atan2()
// function when both parameters are of
// same type
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double x = 10.0, y = 10.0, result;
    result = atan2(y, x);

    cout << "atan2(y/x) = " << result
         << " radians" << endl;
    cout << "atan2(y/x) = " << result * 180 / 3.141592
         << " degrees" << endl;

    return 0;
}
```

**Output:** 

```cpp
atan2(y/x) = 0.785398 radians
atan2(y/x) = 45 degrees
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the atan2()
// function when both parameters are of
// different types
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double result;
    float x = -10.0;
    int y = 10;
    result = atan2(y, x);

    cout << "atan2(y/x) = " << result
         << " radians" << endl;
    cout << "atan2(y/x) = " << result * 180 / 3.141592 << " degrees" << endl;

    return 0;
}
```

**Output:** 

```cpp
atan2(y/x) = 2.35619 radians
atan2(y/x) = 135 degrees
```

**节目 3:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the atan2()
// function when y/x is undefined
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double x = 0.0, y = 10.0, result;
    result = atan2(y, x);

    cout << "atan2(y/x) = " << result
         << " radians" << endl;
    cout << "atan2(y/x) = " << result * 180 / 3.141592
         << " degrees" << endl;

    return 0;
}
```

**Output:** 

```cpp
atan2(y/x) = 1.5708 radians
atan2(y/x) = 90 degrees
```

**节目 4:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the atan2()
// function when both parameters are zero
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double x = 0.0, y = 0.0, result;
    result = atan2(y, x);

    cout << "atan2(y/x) = " << result
         << " radians" << endl;
    cout << "atan2(y/x) = " << result * 180 / 3.141592
         << " degrees" << endl;

    return 0;
}
```

**Output:** 

```cpp
atan2(y/x) = 0 radians
atan2(y/x) = 0 degrees
```

**错误和异常:**当字符串或字符作为参数传递时，函数返回**无匹配函数调用**错误。
**节目 5:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the atan2()
// errors and exceptions
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double x = 0.0, y = 10.0, result;
    result = atan2("1", x);

    cout << "atan2(y/x) = " << result << " radians" << endl;

    cout << "atan2(y/x) = " << result * 180 / 3.141592
         << " degrees" << endl;

    return 0;
}
```

**输出:**

```cpp
prog.cpp:9:26: error: no matching function for call to 'atan2(const char [2], double&)'
     result = atan2("1", x);
```