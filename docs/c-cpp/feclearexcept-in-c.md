# c++ 中的 feclearexcept，带示例

> 原文:[https://www.geeksforgeeks.org/feclearexcept-in-c/](https://www.geeksforgeeks.org/feclearexcept-in-c/)

**feclearexcept()** 清除由 except 表示的支持的浮点异常。
**语法:**

```cpp
int feclearexcept(int excepts);
excepts : Bitmask listing of exception flags to clear
```

**返回值:**
如果所有异常都被清除，或者如果异常等于零，feclearexcept()函数返回零值。
如果出现错误，返回非零值。

要使函数工作，您应该启用 **FENV_ACCESS** ，这将使您的程序能够访问浮点环境来测试引发的异常。

```cpp
// Cpp program to demonstrate
// feclearexcept()
#include <fenv.h> /* feclearexcept FE_ALL_EXCEPT, FE_INVALID */
#include <iostream> /* cout */
#include <math.h> /* sqrt */
#pragma STDC FENV_ACCESS on
using namespace std;

int main()
{
    feclearexcept(FE_ALL_EXCEPT);
    sqrt(-1);
    if (fetestexcept(FE_INVALID))
        cout << "sqrt(-1) raises FE_INVALID" << endl;
    return 0;
}
```

**Output:**

```cpp
sqrt(-1) raises FE_INVALID

```