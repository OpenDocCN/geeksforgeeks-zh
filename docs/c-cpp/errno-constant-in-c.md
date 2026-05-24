# c++ 中的 errno 常量

> 原文:[https://www.geeksforgeeks.org/errno-constant-in-c/](https://www.geeksforgeeks.org/errno-constant-in-c/)

**errno** 是用于错误指示的预处理器宏。

*   程序启动时 **errno** 的值置零，无论是否发生错误，标准 C++ 库的任何函数都允许向 errno 写入正整数。
*   一旦 errno 的值从零变为非零，那么 C++ 标准库中的任何其他函数都不能将其值变为零。errno 在 **cerrno** 头文件中定义。
*   当数学参数有错误时，errno 的值设置为 33。在 C++ 中，数学参数的误差由值为 33 的 **EDOM** 表示。

声明 errno()的同一个头还声明了至少以下值不同于零的宏常数:

*   **EDOM–定义域错误**:一些数学函数只为某些实数值定义，这些实数值称为它的定义域，例如，平方根和对数函数只为非负数定义，所以如果我们在这些函数中传递负参数，它们**将 errno 设置为 EDOM**
*   **ERANGE–范围误差**:一个变量可以表示的数值范围是有限的。例如，像 pow 这样的数学函数可以很容易地将浮点变量表示的范围输出，或者像 strtod 这样的函数可以遇到比可表示的范围值更长的数字序列。**在这些情况下，errno 被设置为 ERANGE。**
*   **eil seq–非法序列**:多字节字符序列可能有一组受限的有效序列。当一组多字节字符被 mbrtowc 等函数翻译时，当遇到无效序列时， **errno 被设置为 EILSEQ。**

以下是实现 **errno** :
**<u>程序 1:</u>** 工作的程序，该程序在 log 函数中传递负值时检测错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <cerrno>
#include <clocale>
#include <cmath>
#include <cstring>
#include <iostream>
using namespace std;

int main()
{
    // log function doesn't take negative value
    // thus it changes value of errno to some positive number
    double not_valid = log(-1.0);

    // check if value of errno same as value of EDOM i.e. 33
    if (errno == EDOM) {
        cout << " Value of errno is : " << errno << '\n';
        cout << " log(-1) is not valid : "
             << strerror(errno) << '\n';
    }
    return 0;
}
```

**Output:** 

```cpp
Value of errno is : 33
 log(-1) is not valid : Numerical argument out of domain
```