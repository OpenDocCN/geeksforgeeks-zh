# C/c++

中的 fegetenv()函数

> 原文:[https://www.geeksforgeeks.org/fegetenv-function-in-c-c/](https://www.geeksforgeeks.org/fegetenv-function-in-c-c/)

C/C++ 中的 **fegetenv()** 函数在头文件 **cfenv.h** 中指定，并尝试将浮点环境的当前状态存储在 **envp** 所指向的对象中。浮点环境是一组状态标志和控制模式，包括浮点异常和舍入方向模式。

**语法:**

```cpp
int fegetenv( fenv_t* envp )
```

**参数:**该函数接受一个强制参数 **envp** ，该参数指定存储浮点环境状态的对象。

**返回值:**该函数返回如下两个值:

*   成功时，它返回零。
*   失败时，它返回非零值。

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate
// fegetenv() function

#include <bits/stdc++.h>
using namespace std;

// rounding direction mode
void rounding_mode()
{
    cout << "Rounding mode is ->";
    switch (fegetround()) {
    case FE_TONEAREST:

        // Round to nearest
        cout << "FE_TONEAREST" << endl;
        break;
    case FE_DOWNWARD:

        // Round downward
        cout << "FE_DOWNWARD" << endl;
        break;
    case FE_UPWARD:

        // Round upward
        cout << "FE_UPWARD" << endl;
        break;
    case FE_TOWARDZERO:

        // Round toward zero
        cout << "FE_TOWARDZERO" << endl;
        break;
    default:
        cout << "unknown" << endl;
    };
}

int main(void)
{
    fenv_t envp;

    // initial environment
    cout << "Initial environment :" << endl;

    // print the exception raised initially
    cout << "Exception raised -> \n";
    if (fetestexcept(FE_ALL_EXCEPT)) {
        if (fetestexcept(FE_DIVBYZERO))
            cout << "FE_DIVBYZERO " << endl;
        if (fetestexcept(FE_INEXACT))
            cout << "FE_INEXACT " << endl;
        if (fetestexcept(FE_INVALID))
            cout << "FE_INVALID " << endl;
        if (fetestexcept(FE_OVERFLOW))
            cout << "FE_OVERFLOW " << endl;
        if (fetestexcept(FE_UNDERFLOW))
            cout << "FE_UNDERFLOW " << endl;
    }
    else
        cout << "None" << endl;

    // print the rounding direction mode
    rounding_mode();

    // Current environment
    fegetenv(&envp);
    feraiseexcept(FE_INVALID);

    // Set rounding direction mode
    fesetround(FE_DOWNWARD);

    // after environment is change
    cout << endl
         << "Final environment :" << endl;

    // print the exception raised
    cout << "Exception raised -> \n";
    if (fetestexcept(FE_ALL_EXCEPT)) {
        if (fetestexcept(FE_DIVBYZERO))
            cout << "FE_DIVBYZERO " << endl;
        if (fetestexcept(FE_INEXACT))
            cout << "FE_INEXACT " << endl;
        if (fetestexcept(FE_INVALID))
            cout << "FE_INVALID " << endl;
        if (fetestexcept(FE_OVERFLOW))
            cout << "FE_OVERFLOW " << endl;
        if (fetestexcept(FE_UNDERFLOW))
            cout << "FE_UNDERFLOW " << endl;
    }
    else
        cout << "None" << endl;

    // print the rounding direction mode
    rounding_mode();

    return 0;
}
```

**Output:**

```cpp
Initial environment :
Exception raised -> 
None
Rounding mode is ->FE_TONEAREST

Final environment :
Exception raised -> 
FE_INVALID 
Rounding mode is ->FE_DOWNWARD

```

**程序 2 :**

```cpp
// C++ program to illustrate
// fegetenv() function

#include <bits/stdc++.h>
using namespace std;

// rounding direction mode
void rounding_mode()
{
    cout << "Rounding mode is ->";
    switch (fegetround()) {
    case FE_TONEAREST:

        // Round to nearest
        cout << "FE_TONEAREST" << endl;
        break;
    case FE_DOWNWARD:

        // Round downward
        cout << "FE_DOWNWARD" << endl;
        break;
    case FE_UPWARD:

        // Round upward
        cout << "FE_UPWARD" << endl;
        break;
    case FE_TOWARDZERO:

        // Round toward zero
        cout << "FE_TOWARDZERO" << endl;
        break;
    default:
        cout << "unknown" << endl;
    };
}

int main(void)
{
    fenv_t envp;

    // initial environment
    cout << "Initial environment :" << endl;

    // print the exception raised initially
    cout << "Exception raised -> \n";
    if (fetestexcept(FE_ALL_EXCEPT)) {
        if (fetestexcept(FE_DIVBYZERO))
            cout << "FE_DIVBYZERO " << endl;
        if (fetestexcept(FE_INEXACT))
            cout << "FE_INEXACT " << endl;
        if (fetestexcept(FE_INVALID))
            cout << "FE_INVALID " << endl;
        if (fetestexcept(FE_OVERFLOW))
            cout << "FE_OVERFLOW " << endl;
        if (fetestexcept(FE_UNDERFLOW))
            cout << "FE_UNDERFLOW " << endl;
    }
    else
        cout << "None" << endl;

    // print the rounding direction mode
    rounding_mode();

    // Current environment
    fegetenv(&envp);
    feraiseexcept(FE_ALL_EXCEPT);

    // Set rounding direction mode
    fesetround(FE_DOWNWARD);

    // after environment is change
    cout << endl
         << "Final environment :" << endl;

    // print the exception raised
    cout << "Exception raised -> \n";
    if (fetestexcept(FE_ALL_EXCEPT)) {
        if (fetestexcept(FE_DIVBYZERO))
            cout << "FE_DIVBYZERO " << endl;
        if (fetestexcept(FE_INEXACT))
            cout << "FE_INEXACT " << endl;
        if (fetestexcept(FE_INVALID))
            cout << "FE_INVALID " << endl;
        if (fetestexcept(FE_OVERFLOW))
            cout << "FE_OVERFLOW " << endl;
        if (fetestexcept(FE_UNDERFLOW))
            cout << "FE_UNDERFLOW " << endl;
    }
    else
        cout << "None" << endl;

    // print the rounding direction mode
    rounding_mode();

    return 0;
}
```

**Output:**

```cpp
Initial environment :
Exception raised -> 
None
Rounding mode is ->FE_TONEAREST

Final environment :
Exception raised -> 
FE_DIVBYZERO 
FE_INEXACT 
FE_INVALID 
FE_OVERFLOW 
FE_UNDERFLOW 
Rounding mode is ->FE_DOWNWARD

```