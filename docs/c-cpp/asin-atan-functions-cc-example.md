# asin()和 atan()在 C/C++ 中的函数，示例

> 原文:[https://www . geesforgeks . org/asin-atan-functions-cc-example/](https://www.geeksforgeeks.org/asin-atan-functions-cc-example/)

在 C++ 中，asin()和 atan()是用于数学计算的预定义函数。 **math.h** 是各种数学函数所需的头文件。这个库中所有可用的函数都以 double 作为参数，并返回 double 作为结果。

**asin()**

asin()函数用来求一个数的反正弦，意思是给这个函数一个 sin 值，它会返回这个值对应的弧度角。在三角测量中，反正弦是正弦的逆运算。
**注意:**传递给此函数的参数必须在 **[-1，1]** 和**范围内，asin()函数**返回的值在 **[-？/2, ?/2].**
**语法:**

```cpp
double asin(double k)

Parameters:
k is the value whose corresponding angle we have to find. 
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// the use of asin function
#include <bits/stdc++.h>
using namespace std;

#define PI 3.14159265

int main()
{
    double k, ret, val;

    // Take any value between [-1, 1]
    k = 0.5;
    // asin() returns value in the range of [-?/2,?/2]
    ret = asin(k);
    val = (ret * 180) / PI;
    cout << "The arcsine of " << k << " is " << ret
         << " radians or " << val << " degrees";

    return 0;
}
```

**输出:**

```cpp
The arcsine of 0.5 is 0.523599 radians or 30 degrees 
```

**阿坦()**

**atan()函数**用来求一个数的反正切，意思是给这个函数一个正切值，它会返回这个值对应的弧度角。反正切是切线的逆运算。该函数接受所有实数， **atan()函数**返回的值在 **[-？/2, ?/2].**
**语法:**

```cpp
double atan(double k)

Parameters:
k is the value whose corresponding angle we have to find.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// the use of atan function
#include <bits/stdc++.h>
using namespace std;

#define PI 3.14159265

int main()
{
    double k, ret, val;

    // Take any value
    k = 1.0;
    ret = atan(k);
    val = (ret * 180) / PI;
    cout << "The arctangent of " << k << " is " << ret
         << " radians or " << val << " degrees";

    return 0;
}
```

**输出:**

```cpp
The arctangent of 1 is 0.785398 radians or 45 degrees 
```