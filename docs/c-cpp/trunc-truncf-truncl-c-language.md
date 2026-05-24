# C 语言的 trunc()、truncf()、truncl()

> 原文:[https://www . geesforgeks . org/trunc-truncf-truncl-c-language/](https://www.geeksforgeeks.org/trunc-truncf-truncl-c-language/)

这三个函数都用于删除小数点后的数字，并返回修改后的十进制数。

**trunc() :** 在小数点后截断一个双精度值，并给出整数部分作为结果。返回值和参数的类型是 double。

> **语法:**
> 双 trunc(double x)；
> 
> **参数:**
> **x :** 取一个双精度值作为输入，然后截断小数点后的值。
> 
> **返回值:**
> 返回一个双精度值，小数点后的值只有 0。

示例:

```cpp
Input : 3.5
Output : 3.0

Input : -3.8
Output : -3.0

```

```cpp
// C program to demonstrate 
// trunc() function
#include <stdio.h>

// library containing trunc function
#include <math.h>     

// Driver function
int main()
{
    // using trunc function which return
    // Truncated value of the input 
    double x1 = 2.0, x2 = 3.9, x3 = -3.3, x4 = 4.9;
    printf(" Truncated value is %lf \n", trunc(x1) );
    printf(" Truncated value is %lf \n", trunc(x2) );

    // For negative values
    printf(" Truncated value is %lf \n", trunc(x3) );
    printf(" Truncated value is %lf \n", trunc(x4) ); 
    return 0;
}
```

**Output:**

```cpp
Truncated value is 2.000000 
 Truncated value is 3.000000 
 Truncated value is -3.000000 
 Truncated value is 4.000000

```

**truncf() :** 它的工作原理与 trunc 相同，区别在于它是用于 float 而不是 double。获取浮点值，删除小数点后的数字并返回修改后的浮点值。

> **语法:**
> float truncf(float x)；
> 
> **参数:**
> **x :** 取一个浮点值作为输入，然后截断小数点后的值。
> 
> **返回值:**
> 返回一个浮点数，小数点后的值只有 0。

示例:

```cpp
Input : 4.5
Output : 4.0

Input : -2.8
Output : -2.0

```

```cpp
// C program to demonstrate truncf() function
#include <stdio.h>
#include <math.h>     

// Driver function
int main()
{
    float x1 = 2.0, x2 = 3.9, x3 = -3.3, x4 = 4.9;

    // using truncf function which return
    // Truncated value of the input 
    printf(" Truncated value is %f \n", truncf(x1) );
    printf(" Truncated value is %f \n", truncf(x2) );

    // For negative values
    printf(" Truncated value is %f \n", truncf(x3) );
    printf(" Truncated value is %f \n", truncf(x4) ); 
    return 0;
}
```

**Output:**

```cpp
Truncated value is 2.000000 
 Truncated value is 3.000000 
 Truncated value is -3.000000 
 Truncated value is 4.000000

```

**truncl() :** 这与 trunc()和 truncf()在长双功能方面相似

> **语法:**
> 长双 truncl(长双 x)；
> 
> **参数:**
> **x :** 取一个长的双精度值作为输入，然后截断小数点后的值。
> 
> **返回值:**
> 返回一个十进制值，小数点后的值只有 0。

示例:

```cpp
Input : 4351.5
Output : 4351.0

Input : -2008.8
Output : -2008.0

```

**正值情况下:**

```cpp
// C program to demonstrate truncl() function
#include <stdio.h>
#include <math.h>     

// Driver function
int main()
{
    long double x1 = 2.0, x2 = 3.9, x3 = -3.3, x4 = 4.9;

    // using truncf function which return
    // Truncated value of the input 
    printf(" Truncated value is %Lf \n", truncl(x1) );
    printf(" Truncated value is %Lf \n", truncl(x2) );

    // For negative values
    printf(" Truncated value is %Lf \n", truncl(x3) );
    printf(" Truncated value is %Lf \n", truncl(x4) ); 
    return 0;
}
```

**Output:**

```cpp
Truncated value is 2.000000 
 Truncated value is 3.000000 
 Truncated value is -3.000000 
 Truncated value is 4.000000

```

每当我们需要从双数据类型计算整数部分时，我们都可以使用 trunc()函数。这个函数的优点是无论十进制值是多少，整数部分都保持不变。在[天花板或地板](https://www.geeksforgeeks.org/ceil-floor-functions-cpp/)或倒圆角函数中，整数值会改变，但在 trunc 函数中不会。