# c++ STL 中的 asinh()函数

> 原文:[https://www.geeksforgeeks.org/asinh-function-in-c-stl/](https://www.geeksforgeeks.org/asinh-function-in-c-stl/)

**asinh()** 是 C++ STL 中的一个内置函数，它返回以弧度表示的给定角度的反双曲正弦值。该功能属于 **< cmath >** 头文件。

**语法:**

```cpp
asinh(data_type x)
```

**参数:**该函数接受一个强制参数 *x* ，该参数以弧度指定反双曲角。它可以是任何值，即负值、正值或零。参数可以是 double、float 或 long double 数据类型。

**返回值:**该函数返回参数的反双曲正弦值，单位为弧度。

根据 **C++ 11 标准**，有各种原型可供 **asinh()** 功能:

<figure class="table">

| 数据类型 | 原型 |
| --- | --- |
| 对于 int | 双 asinh(t val)； |
| For the float | Is a float (float valve); |
| Weishuang | 另一只提琴: |
| Weichangshuang | Is long double asinh (long double val); |

</figure>

这里， **val** 是变量。

**例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the asinh() function
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    double x = 50.0;

    // Function call to calculate asinh(x) value
    double result = asinh(x);

    cout << "asinh(50.0) = " << result << " radians"
         << endl;
    cout << "asinh(50.0) = " << result * 180 / 3.141592
         << " degrees" << endl;
    return 0;
}
```

**Output**

```cpp
asinh(50.0) = 4.60527 radians
asinh(50.0) = 263.863 degrees
```

**例 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the asinh() function
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    int x = -50.0;

    // Function call to calculate asinh(x) value
    double result = asinh(x);

    cout << "asinh(-50.0) = " << result << " radians"
         << endl;
    cout << "asinh(-50.0) = " << result * 180 / 3.141592
         << " degrees" << endl;
    return 0;
}
```

**Output**

```cpp
asinh(-50.0) = -4.60527 radians
asinh(-50.0) = -263.863 degrees
```

**错误和异常:**当将**字符串或字符**作为参数传递时，该函数返回**无匹配函数调用错误**。

**例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate errors in
// the asinh() function
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    string x = "gfg";

    // Function call to calculate asinh(x) value
    double result = asinh(x);

    cout << "asinh(50.0) = " << result << " radians"
         << endl;
    cout << "asinh(50.0) = " << result * 180 / 3.141592
         << " degrees" << endl;
    return 0;
}
```

**错误:**

```cpp
prog.cpp: In function ‘int main()’:
prog.cpp:12:28: error: no matching function for call to ‘asinh(std::__cxx11::string&)’
     double result = asinh(x);
```

上述程序产生错误**没有匹配函数调用**作为**字符串**作为参数传递。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。