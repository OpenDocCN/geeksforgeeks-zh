# c++ STL 中的 atanh()函数

> 原文:[https://www.geeksforgeeks.org/atanh-function-in-c-stl/](https://www.geeksforgeeks.org/atanh-function-in-c-stl/)

**atanh()** 是 C++ STL 中的一个内置函数，它返回以弧度为单位的给定角度的反双曲正切值。该功能属于 **< cmath >** 头文件。

**语法:**

```cpp
atanh(data_type x)
```

**参数:**该函数接受一个强制参数 *x* ，该参数以弧度为单位指定位于[-1，1]范围内的反双曲角。参数可以是 double、float 或 long double 数据类型。

**返回值:**该函数根据参数中传递的参数，以弧度为单位返回参数的反双曲正弦值。下表给出了不同的返回值:

<figure class="table">

| 传递的参数(x) | 返回值 |
| --- | --- |
| -1 | 有限数值 |
| x>1 或 x | 非数字 |
| x=-1 | -inf |
| x=1 | +inf |

</figure>

根据 **C++ 11 标准**，有各种原型可用于 **atanh()** 功能，

<figure class="table">T5T7数据类型T10【原型】T11T13T15为两倍T18】double atanh(double x)；</figure>

从(int、float 或 long double)到 double 需要显式转换，

<figure class="table">

| 数据类型 | 原型 |
| --- | --- |
| For int | int a = 0；double b = atanh(double(a))； |
| To float | 浮动 a = 0；double b = atanh(double(a))； |
| Weichangshuang | 长双 a = 0；双 b = atanh(双(a))；

 |

</figure>

下面的程序说明了上述方法:

**例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// the atanh() function
// all return values
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Return value when -1<x<1
    int x = 0;
    // Function call to calculate atanh(x) value
    double result = atanh(x);

    cout << "atanh(0) = " << result << " radians\n";
    cout << "atanh(0) = " << result * 180 / 3.141592
         << " degrees\n";

    // Return value when x=-1
    x = -1;
    result = atanh(x);

    cout << "\natanh(-1) = " << result << " radians\n";
    cout << "atanh(-1) = " << result * 180 / 3.141592
         << " degrees\n";

    // Return value when x=1
    x = 1;
    result = atanh(x);

    cout << "\natanh(1) = " << result << " radians\n";
    cout << "atanh(1) = " << result * 180 / 3.141592
         << " degrees\n";

    // Return value when x<-1 or x>1
    x = -2;
    result = atanh(x);

    cout << "\natanh(-2) = " << result << " radians\n";
    cout << "atanh(-2) = " << result * 180 / 3.141592
         << " degrees\n";

    return 0;
}
```

**Output**

```cpp
atanh(0) = 0 radians
atanh(0) = 0 degrees

atanh(-1) = -inf radians
atanh(-1) = -inf degrees

atanh(1) = inf radians
atanh(1) = inf degrees

atanh(-2) = -nan radians
atanh(-2) = -nan degrees
```

**错误和异常:**当传递了一个**字符串或任何其他数据类型**时，函数返回一个**无匹配函数错误消息**。

**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the atanh() function
// string passed
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string x = "gfg";

    // Function call to calculate atanh(x) value
    double result = atanh(x);

    cout << "atanh(50.0) = " << result << " radians"
         << endl;
    cout << "atanh(50.0) = " << result * 180 / 3.141592
         << " degrees" << endl;
    return 0;
}
```

如果没有匹配函数将作为**字符串**作为参数传递，上述程序将产生**错误。**

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。