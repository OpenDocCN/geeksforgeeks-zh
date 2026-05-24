# c++ STL 中的 ilogb()函数

> 原文:[https://www.geeksforgeeks.org/ilogb-function-in-c-stl/](https://www.geeksforgeeks.org/ilogb-function-in-c-stl/)

C++ STL 中的 **ilogb(x)** 函数返回|x|的对数的整数部分，使用 **FLT_RADIX** 作为对数的底数。一般来说，FLT_RADIX 的值为 2，因此 ilogb()相当于 ilog2()(仅适用于正值)。

**语法**:

```cpp
ilogb(x)
```

**参数**:该函数接受单个强制参数 x，其 ilogb()将被计算。数据类型可以是 double、float、long double 或 int。
**返回值:**该函数返回|x|对数的整数部分，使用 FLT_RADIX 作为对数的基数。该函数返回三个异常值:

*   如果参数为 NaN，则返回 **FP_LOGBNAN** 。
*   如果参数为无穷大，则返回 **INT_MAX**
*   如果参数为 0，则返回 **FP_LOGB0** 。

以下程序说明上述功能:
**程序 1** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the ilogb()
// function when input is an integer
#include <cfloat>
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    int result, x = 25;

    // Function to calculate ilogb(25)
    result = ilogb(x);
    cout << "ilogb (" << x << ") = " << result << endl;

    // Function to calculate ilogb(50)
    x = 50;
    result = ilogb(x);
    cout << "ilogb (" << x << ") = " << result << endl;

    return 0;
}
```

**Output:** 

```cpp
ilogb (25) = 4
ilogb (50) = 5
```

**程序 2** :
非整数型程序

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the ilogb()
// function when input is a double value
#include <cfloat>
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    int result, x = 11.11;

    result = ilogb(x);
    cout << "ilogb (" << x << ") = " << result << endl;

    x = 41.11;
    result = ilogb(x);
    cout << "ilogb (" << x << ") = " << result << endl;

    return 0;
}
```

**Output:** 

```cpp
ilogb (11) = 3
ilogb (41) = 5
```

**程序 3** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the ilogb()
// function when input is 0
#include <cfloat>
#include <cmath>
#include <iostream>
#include <iostream>

using namespace std;

int main()
{
    int result, x = 0;

    result = ilogb(x);
    cout << "ilogb (" << x << ") = " << result << endl;

    return 0;
}
```

**Output:** 

```cpp
ilogb (0) = -2147483648
```