# c++ STL 中的 acosh()函数

> 原文:[https://www.geeksforgeeks.org/acosh-function-in-c-stl/](https://www.geeksforgeeks.org/acosh-function-in-c-stl/)

**acosh()** 是 C++ STL 中的一个内置函数，它返回以弧度表示的角度的反双曲余弦值。该功能属于 **< cmath >** 头文件。

**语法:**

```cpp
acosh(data_type x)
```

**参数:**该函数接受一个强制参数 x，该参数指定弧度的反双曲角应大于或等于 1。如果参数小于 1，则返回-nan。参数可以是 double、float 或 long double 数据类型。

**返回:**acosh()函数返回参数的反双曲正弦值，单位为弧度，范围为**【0，inf】。**

根据 **C++ 11 标准**，有各种原型可供 **acosh()** 功能、

<figure class="table">T5T7数据类型T10【原型】 为两倍double acosh(double x)；</figure>

从(int、float 或 long double)到 double 需要显式转换，

<figure class="table">

| 数据类型 | 原型 |
| --- | --- |
| For int | int a = 0；double b = acosh(double(a))； |
| To float | 浮动 a = 0；double b = acosh(double(a))； |
| Weichangshuang | 长双 a = 0；double b = acosh(double(a))；

 |

</figure>

以下程序说明了上述方法:

**例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the acosh() function
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    double x = 50.0;

    // Function call to calculate acosh(x) value
    double result = acosh(x);

    cout << "acosh(50.0) = " << result << " radians"
         << endl;
    cout << "acosh(50.0) = " << result * 180 / 3.141592
         << " degrees" << endl;
    return 0;
}
```

**Output**

```cpp
acosh(50.0) = 4.60507 radians
acosh(50.0) = 263.851 degrees
```

**例 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the acosh() function
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    int x = 40.0;

    // Function call to calculate acosh(x) value
    double result = acosh(x);

    cout << "acosh(40.0) = " << result << " radians"
         << endl;
    cout << "acosh(40.0) = " << result * 180 / 3.141592
         << " degrees" << endl;
    return 0;
}
```

**Output**

```cpp
acosh(40.0) = 4.38187 radians
acosh(40.0) = 251.063 degrees
```

如果我们传递一个负值(小于 1 的值)，函数返回 **NaN(不是数字)。**

**例 3:**

## C++

```cpp
// C++ program to demonstrate
// the acosh() function
// value less than 1
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    double x = -50.0;

    // Function call to calculate acosh(x) value
    double result = acosh(x);

    cout << "acosh(-50.0) = " << result << " radians"
         << endl;
    cout << "acosh(-50.0) = " << result * 180 / 3.141592
         << " degrees" << endl;
    return 0;
}
```

**Output**

```cpp
acosh(-50.0) = -nan radians
acosh(-50.0) = -nan degrees
```

**错误和异常:**当字符串或字符作为参数传递时，函数返回**无匹配函数调用错误**。

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the acosh() function
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    string x = "gfg";

    // Function call to calculate acosh(x) value
    double result = acosh(x);

    cout << "acosh(50.0) = " << result << " radians"
         << endl;
    cout << "acosh(50.0) = " << result * 180 / 3.141592
         << " degrees" << endl;
    return 0;
}
```

**错误:**

```cpp
prog.cpp: In function ‘int main()’:
prog.cpp:12:28: error: no matching function for call to ‘acosh(std::__cxx11::string&)’
     double result = acosh(x);
```

如果**没有匹配的函数调用**作为**字符串**作为参数传递，上述程序会产生错误。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。