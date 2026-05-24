# c++ 中的 log1p()

> 原文:[https://www.geeksforgeeks.org/log1p-in-cpp/](https://www.geeksforgeeks.org/log1p-in-cpp/)

log1p()函数接受参数 x，并返回 x+1 的以 e 为底的对数的自然对数。这里 e 是一个数学常数，值等于 2.71828。

**语法:**

```cpp
double log1p (double x);
float log1p (float x);
long double log1p (long double x);

```

> **参数:**
> 
> *   log1p()函数接受[-1，]范围内的单个参数。].*   If we pass the value which is less than -1, log1p() returns Nan (Not a Number).
>     
>     **返回:**
>     
>     
>     
>     *   正数:如果 **x > 0***   如果 **x=0** ，则为零*   如果 **-1 > x > 0** ，则为负数*   -?(-无穷大)如果 **x=-1***   NaN if **x < -1**

**错误和异常:**

1.  必须给出这两个参数，否则会给出错误**调用“log1p()”**没有匹配的函数。
2.  如果我们将字符串作为参数传递，我们将得到 errorb **没有匹配的函数来调用‘log1p(const char[n])**。
3.  如果我们通过-1，它会给出 **-inf** 。
4.  如果我们通过 0，它会给**零**。

**示例:**

```cpp
Input  : log1p(50.35)
Output :  3.93866

```

```cpp
Input  : log1p(143)
Output : 4.96981

```

**#代码 1**

```cpp
// CPP program to illustrate log1p()
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    double x = 50.35, answer;

    // returns logarithm of 51.35 base e
    answer = log1p(x);
    cout << "log1p(" << x << ") = " 
         << answer << endl;

    return 0;
}
```

**Output:**

```cpp
log1p(50.35) = 3.93866

```

**#代码 2**

```cpp
// CPP program to illustrate log1p()
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    double answer;
    int x = 143;

    // returns logarithm of 144 base e
    answer = log1p(x);
    cout << "log1p(" << x << ") = " 
         << answer << endl;

    return 0;
}
```

**Output:**

```cpp
log1p(143) = 4.96981

```

**实际用途:**

*   它实际上用于获取给定参数+1 的对数值。