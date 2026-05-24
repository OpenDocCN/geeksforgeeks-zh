# c++ STL 中的 logb()函数

> 原文:[https://www.geeksforgeeks.org/logb-function-in-c-stl/](https://www.geeksforgeeks.org/logb-function-in-c-stl/)

**logb()** 是 C++ STL 中的一个内置函数，返回|x|的对数，使用 FLT_RADIX 作为对数的基数。一般来说，FLT_RADIX 的值为 2，因此 logb()相当于 log2()(仅适用于正值)。

**语法**:

```cpp
logb(val)
```

**参数**:该函数接受单个强制参数值，该参数值指定要计算 logb()的值。数据类型可以是 double、float、long double 或 int。

**返回类型**:函数返回|x|的对数。

以下程序说明了上述功能:

**程序 1** :

```cpp
// C++ program to illustrate
// to implement logb() function
// when data-type is integer
#include <cmath>
#include <iostream>
using namespace std;
int main()
{
    double result;
    int x = -10;

    result = logb(x);
    cout << "logb(" << x << ") = "
         << "log(|" << x << "|) = " << result << endl;

    x = 10;

    result = logb(x);
    cout << "logb(" << x << ") = "
         << "log(|" << x << "|) = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
logb(-10) = log(|-10|) = 3
logb(10) = log(|10|) = 3

```

**程序 2** :

```cpp
// C++ program to illustrate
// to implement logb() function
// when data-type is double
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    double x = 70.56, result;

    result = logb(x);
    cout << "logb(" << x << ") = "
         << "log(|" << x << "|) = " << result << endl;

    x = 17.6;

    result = logb(x);
    cout << "logb(" << x << ") = "
         << "log(|" << x << "|) = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
logb(70.56) = log(|70.56|) = 6
logb(17.6) = log(|17.6|) = 4

```

**程序 3** :

```cpp
// C++ program to illustrate
// to implement logb() function
// when input is 0
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    double result;
    int x = 0;

    result = logb(x);
    cout << "logb(" << x << ") = "
         << "log(|" << x << "|) = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
logb(0) = log(|0|) = -inf

```