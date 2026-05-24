# C/c++

中的 feholdexcept()

> 原文:[https://www.geeksforgeeks.org/feholdexcept-in-c-c/](https://www.geeksforgeeks.org/feholdexcept-in-c-c/)

C/C++ 中的 **feholdexcept()** 函数首先将当前浮点环境保存在 fenv_t 的对象中，然后重置所有浮点状态标志的当前值。feholdexcept()函数在 **C++** 中的 **cfenv** 头文件和 **C** 中的 **fenv.h** 头文件中定义。
**语法:**

```cpp
int feholdexcept( fenv_t* envp )
```

**参数:**该函数接受单个强制参数 **envp** ，该参数是指向类型为 **fenv_t** 的对象
的指针，该对象存储浮点环境的当前状态。
**返回值:**函数在两个条件下返回一个 int 值:

*   如果函数成功完成，则返回 0。
*   失败时，它返回一个非零整数。

下面的程序说明了上述功能。
**节目 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// feholdexcept() function
#include <bits/stdc++.h>
#pragma STDC FENV_ACCESS on

// function to divide
double divide(double x, double y)
{
    // environment variable
    fenv_t envp;

    // do the devision
    double ans = x / y;

    // use the function feholdexcept
    feholdexcept(&envp);

    // clears exception
    feclearexcept(FE_OVERFLOW | FE_DIVBYZERO);

    return ans;
}

int main()
{
    // It is a combination of all of
    // the possible floating-point exception
    feclearexcept(FE_ALL_EXCEPT);
    double x = 10;
    double y = 0;

    // it returns the division of x and y
    printf("x/y = %f\n", divide(x, y));

    // the function does not throw
    // any exception on division by 0
    if (!fetestexcept(FE_ALL_EXCEPT)) {
        printf("No exceptions raised");
    }
    return 0;
}
```

**Output:** 

```cpp
x/y = inf
No exceptions raised
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// feholdexcept() function
#include <bits/stdc++.h>
#pragma STDC FENV_ACCESS on
using namespace std;

// function to print raised exceptions
void raised_exceptions()
{
    cout << "Exceptions raised are : ";

    if (fetestexcept(FE_DIVBYZERO))
        cout << " FE_DIVBYZERO\n";
    else if (fetestexcept(FE_INVALID))
        cout << " FE_INVALID\n";
    else if (fetestexcept(FE_OVERFLOW))
        cout << " FE_OVERFLOW\n";
    else if (fetestexcept(FE_UNDERFLOW))
        cout << " FE_UNDERFLOW\n";
    else
        cout << " No exception found\n";

    return;
}

// Driver code
int main()
{
    // environment variable
    fenv_t envp;

    // raise certain exceptions
    feraiseexcept(FE_DIVBYZERO);
    // print the raised exception
    raised_exceptions();

    // saves and clears current
    // exceptions by feholdexcept function
    feholdexcept(&envp);
    // no exception found
    raised_exceptions();

    // restores the previously
    // saved exceptions
    feupdateenv(&envp);
    raised_exceptions();

    return 0;
}
```

**Output:** 

```cpp
Exceptions raised are :  FE_DIVBYZERO
Exceptions raised are :  No exception found
Exceptions raised are :  FE_DIVBYZERO
```