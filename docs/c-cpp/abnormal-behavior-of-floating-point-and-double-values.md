# 浮点和双值异常行为

> 原文:[https://www . geesforgeks . org/浮点和双值异常行为/](https://www.geeksforgeeks.org/abnormal-behavior-of-floating-point-and-double-values/)

[**Float**](https://www.geeksforgeeks.org/introduction-of-floating-point-representation/) 是一个 32 位 IEEE 754 单精度浮点数，1 位为符号，(8 位为指数，23*为数值)，即 Float 有 7 位小数精度。

[**Double**](https://www.geeksforgeeks.org/difference-float-double-c-cpp/) 是一个 64 位 IEEE 754 双精度浮点数(1 位为符号，11 位为指数，52*位为数值)，即 Double 有 15 位小数精度。

本文主要讨论浮点值和双精度值的异常行为。

**程序 1:**

## C

```cpp
// C program to illustrate the abnormal
// behaviours of floating point value
#include <stdio.h>

// Driver Code
int main()
{
    float f = 0.2;
    if (f == 0.2)
        printf("it's geek time");
    else if (f < 0.2)
        printf("it's party time");
    else
        printf("it's movie time");
    return 0;
}
```

## C++

```cpp
// C++ program to illustrate the abnormal
// behaviours of floating point value
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    float f = 0.2;
    if (f == 0.2)
        cout << "it's geek time";
    else if (f < 0.2)
        cout << "it's party time";
    else
        cout << "it's movie time";
    return 0;
}
```

**Output:**

```cpp
it's movie time

```

**说明:**在上面的节目中，输出的是“现在是电影时间”，而不是“现在是极客时间”。因此，这里的解释是，由于 f 是一个浮点值，“0.2”是一个双精度值，因此由于两种数据类型的精度差异，可以看到这种异常行为。在语句中，如果(f==0.2)， **f 与 0.2 进行比较，因此内部是这样写的:**

```cpp
**if((double)(float)(0.2) == (0.2))**
```

**由于 0.2 是在上面一行中声明和赋值时第一次转换为 float(由于这个原因，精度会降低，并且在某个值和某些信息/精度丢失后它会被舍入)，在这之后，它在 if 语句中再次转换为 double，但是丢失的值不能被取回。因此，可以看到这种行为。**

**为了更清楚地理解，让我们举一个基数为 10 的数字系统的例子(类比)。**

**让我们取 10/3，将其表示为 5 个有效数字:3.3333 或 3.3334(在四舍五入的情况下)。这就是“浮点”f。现在将 **f** 的值转换为一个有 8 个有效数字的值(f 转换为“双”)- 3.3333000 或 3.3334000(四舍五入的情况下)。那不等于 3.3333333(10/3 的值直接作为替身)。**

### ****<u>避免异常行为的方法</u> :****

****在声明/初始化变量时，用 double f = 0.2 或 long double f = 0.2 替换 float f = 0.2:****

**下面是 C/C++ 程序来说明上面的思路:**

**T3】CT5

```cpp
// C program to illustrate the above idea
#include <stdio.h>

// Driver Code
int main()
{
    // Declare as double or long double
    // or long double f = 0.2;
    double f = 0.2;
    if (f == 0.2)
        printf("it's geek time");
    else if (f < 0.2)
        printf("it's party time");
    else
        printf("it's movie time");

    return 0;
}
```

T6

## c++

T9

```cpp
// C program to illustrate the above idea
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Declare as double or long double
    // or long double f = 0.2;
    double f = 0.2;
    if (f == 0.2)
        cout << "it's geek time";
    else if (f < 0.2)
        cout << "it's party time";
    else
        cout << "it's movie time";
    return 0;
}
```

T10****T12**输出:**T15】

```cpp
it's geek time

```**