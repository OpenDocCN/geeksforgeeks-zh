# exp2()函数在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/exp2-function-in-c-stl/](https://www.geeksforgeeks.org/exp2-function-in-c-stl/)

**exp2()** 是 C++ STL 中的一个内置函数，用于计算给定数字的基数为 2 的指数函数。也可以写成 2 <sup>num</sup> 。
**语法** :

```cpp
exp2(data_type num)
```

**参数**:该函数接受一个指定指数值的强制参数**数**。它可以是正的、负的或 0。参数可以是 double、float 或 long double 类型。
**返回值**:返回双精度、浮点或长双精度值，相当于 2 <sup>num</sup> 。
**程序 1** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// exp2() function for negative double numbers
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    double n = -3.14;

    double ans = exp2(n);
    cout << "exp2(-3.14) = " << ans << endl;

    return 0;
}
```

**Output:** 

```cpp
exp2(-3.14) = 0.11344
```

**节目 2** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// exp2() function for positive numbers
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    int n = 6;

    int ans = exp2(n);
    cout << "exp2(6) = " << ans << endl;

    return 0;
}
```

**Output:** 

```cpp
exp2(6) = 64
```

**节目 3** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// exp2() function for 0
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    int n = 0;

    int ans = exp2(n);
    cout << "exp2(0) = " << ans << endl;

    return 0;
}
```

**Output:** 

```cpp
exp2(0) = 1
```

**错误和异常:**如果结果的幅度太大，无法用返回类型的值来表示，则函数返回带适当符号的巨 _ 瓦尔(或巨 _ 瓦尔或巨 _VALL)，并出现*溢出范围错误*。
下面程序举例说明错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// exp2() function for range overflow
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    // overflow will occur as 2^100 will not
    // fit to int data-type
    int n = 100;

    int ans = exp2(n);
    cout << "exp2(100) = " << ans << endl;

    return 0;
}
```

**Output:** 

```cpp
exp2(100) = -2147483648
```