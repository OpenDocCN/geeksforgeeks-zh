# C/C++ 中的 `fegetexceptflag()` 函数

> 原文: [https://www.geeksforgeeks.org/fegetexceptflag-function-in-c-c/](https://www.geeksforgeeks.org/fegetexceptflag-function-in-c-c/)

C/C++ 中的 `fegetexceptflag()` 函数在头文件 `fenv.h` 中指定，用于获取浮点异常标志。该功能将引发的异常存储在 `flag` 指定的点。

## 语法

```cpp
int fegetexceptflag(fexcept_t* flagp, int excepts)
```

## 参数

该功能接受两个强制参数，如下所述:

*   `flagp`: 表示指向存储表示的 `fexcept_t` 对象的指针。
*   `excepts`: 表示位掩码值。

## 宏描述

1.  `FE_DIVBYZERO`: 极点误差:除以零。
2.  `FE_INEXACT`: INEXACT:结果不准确。
3.  `FE_INVALID`: 域错误:至少有一个参数是未定义函数的值。
4.  `FE_OVERFLOW`: 溢出范围错误:结果过大。
5.  `FE_UNDERFLOW`: underfly 范围误差:结果太小。
6.  `FE_ALL_EXCEPT`: 所有例外。

## 返回值

该函数返回如下两个值:

*   零: 关于成功。
*   非零: 故障时

## 示例程序

以下程序说明了上述功能:

### 程序 1

```cpp
// C++ program to illustrate
// fegetexceptflag() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // bitmask value
    fexcept_t excepts;

    // divided by zero exception
    feraiseexcept(FE_DIVBYZERO);

    // current state is saved
    fegetexceptflag(&excepts, FE_ALL_EXCEPT);
    cout << "Exception raised -> \n";

    // print the exception occurred
    if (fetestexcept(FE_ALL_EXCEPT)) {
        if (fetestexcept(FE_DIVBYZERO))
            cout << "FE_DIVBYZERO \n";
        if (fetestexcept(FE_INEXACT))
            cout << "FE_INEXACT \n";
        if (fetestexcept(FE_INVALID))
            cout << "FE_INVALID \n";
        if (fetestexcept(FE_OVERFLOW))
            cout << "FE_OVERFLOW \n";
        if (fetestexcept(FE_UNDERFLOW))
            cout << "FE_UNDERFLOW \n";
        if (fetestexcept(FE_ALL_EXCEPT))
            cout << "FE_ALL_EXCEPT \n";
    }
    else
        cout << "None";

    return 0;
}
```

**输出:**

```cpp
Exception raised -> 
FE_DIVBYZERO 
FE_ALL_EXCEPT
```

### 程序 2

```cpp
// C++ program to illustrate
// fegetexceptflag() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // bitmask value
    fexcept_t excepts;

    // raised exception
    feraiseexcept(FE_ALL_EXCEPT);

    // current state is saved
    fegetexceptflag(&excepts, FE_ALL_EXCEPT);
    cout << "Exception raised -> \n";

    // print the exception occurred
    if (fetestexcept(FE_ALL_EXCEPT)) {
        if (fetestexcept(FE_DIVBYZERO))
            cout << "FE_DIVBYZERO \n";
        if (fetestexcept(FE_INEXACT))
            cout << "FE_INEXACT \n";
        if (fetestexcept(FE_INVALID))
            cout << "FE_INVALID \n";
        if (fetestexcept(FE_OVERFLOW))
            cout << "FE_OVERFLOW \n";
        if (fetestexcept(FE_UNDERFLOW))
            cout << "FE_UNDERFLOW \n";
        if (fetestexcept(FE_ALL_EXCEPT))
            cout << "FE_ALL_EXCEPT \n";
    }
    else
        cout << "None";

    return 0;
}
```

**输出:**

```cpp
Exception raised -> 
FE_DIVBYZERO 
FE_INEXACT 
FE_INVALID 
FE_OVERFLOW 
FE_UNDERFLOW 
FE_ALL_EXCEPT
```