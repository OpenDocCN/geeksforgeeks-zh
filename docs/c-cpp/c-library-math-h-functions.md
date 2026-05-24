# C 库数学函数

> 原文:[https://www.geeksforgeeks.org/c-library-math-h-functions/](https://www.geeksforgeeks.org/c-library-math-h-functions/)

**数学. h** 标题定义了各种数学函数和一个宏。这个库中所有可用的函数都以**双**为自变量，返回**双**为结果。让我们逐一讨论一些重要的功能。
1。**double ceil(double x)**:C 库函数 double ceil(double x)返回大于等于 x 的最小整数值。

```cpp
syntax : double ceil(double x)
```

## C

```cpp
// C code to illustrate
// the use of ceil function.
#include <stdio.h>
#include <math.h>

int main ()
{
float val1, val2, val3, val4;

val1 = 1.6;
val2 = 1.2;
val3 = -2.8;
val4 = -2.3;

printf ("value1 = %.1lf\n", ceil(val1));
printf ("value2 = %.1lf\n", ceil(val2));
printf ("value3 = %.1lf\n", ceil(val3));
printf ("value4 = %.1lf\n", ceil(val4));

return(0);
}
```

输出:

```cpp
value1 = 2.0
value2 = 2.0
value3 = -2.0
value4 = -2.0
```

2.**双层(双 x):**C 库函数双层(双 x)返回小于或等于 x 的最大整数值。

```cpp
syntax : double floor(double x)
```

## C

```cpp
// C code to illustrate
// the use of floor function
#include <stdio.h>
#include <math.h>

int main ()
{
   float val1, val2, val3, val4;

   val1 = 1.6;
   val2 = 1.2;
   val3 = -2.8;
   val4 = -2.3;

   printf("Value1 = %.1lf\n", floor(val1));
   printf("Value2 = %.1lf\n", floor(val2));
   printf("Value3 = %.1lf\n", floor(val3));
   printf("Value4 = %.1lf\n", floor(val4));

   return(0);
}
```

输出:

```cpp
Value1 = 1.0
Value2 = 1.0
Value3 = -3.0
Value4 = -3.0
```

3.**双 fabs(double x)**:C 库函数 double fabs(double x)返回 x 的绝对值。

```cpp
syntax : double fabs(double x)
```

## C

```cpp
// C code to illustrate
// the use of fabs function
#include <stdio.h>
#include <math.h>

int main ()
{
   int a, b;
   a = 1234;
   b = -344;

   printf("The absolute value of %d is %lf\n", a, fabs(a));
   printf("The absolute value of %d is %lf\n", b, fabs(b));

   return(0);
}
```

输出:

```cpp
The absolute value of 1234 is 1234.000000
The absolute value of -344 is 344.000000
```

4.**双对数(双 x)**:C 库函数双对数(双 x)返回 x 的自然对数(以 e 为底的对数)

```cpp
syntax : double log(double x)
```

## C

```cpp
// C code to illustrate
// the use of log function

#include <stdio.h>
#include <math.h>

int main ()
{
   double x, ret;
   x = 2.7;

   /* finding log(2.7) */
   ret = log(x);
   printf("log(%lf) = %lf", x, ret);

   return(0);
}
```

输出:

```cpp
log(2.700000) = 0.993252
```

5.**double log10(double x)**:C 库函数 double log10(double x)返回 x 的公共对数(以 10 为底的对数)

```cpp
syntax : double log10(double x)
```

## C

```cpp
// C code to illustrate
// the use of log10 function
#include <stdio.h>
#include <math.h>

int main ()
{
   double x, ret;
   x = 10000;

   /* finding value of log1010000 */
   ret = log10(x);
   printf("log10(%lf) = %lf\n", x, ret);

   return(0);
}
```

输出:

```cpp
log10(10000.000000) = 4.000000
```

6. **double fmod(double x，double y)**:C 库函数 double fmod(double x，double y)返回 x 除以 y 的余数。

```cpp
syntax : double fmod(double x, double y) 
```

## C

```cpp
// C code to illustrate
// the use of fmod function
#include <stdio.h>
#include <math.h>

int main ()
{
   float a, b;
   int c;
   a = 8.2;
   b = 5.7;
   c = 3;
   printf("Remainder of %f / %d is %lf\n", a, c, fmod(a, c));
   printf("Remainder of %f / %f is %lf\n", a, b, fmod(a, b));

   return(0);
}
```

输出:

```cpp
Remainder of 8.200000 / 3 is 2.200000
Remainder of 8.200000 / 5.700000 is 2.500000
```

7.**double sqrt(double x)**:C 库函数 double sqrt(double x)返回 x 的平方根.

```cpp
syntax : double sqrt(double x)
```

## C

```cpp
// C code to illustrate
// the use of sqrt function
#include <stdio.h>
#include <math.h>

int main ()
{

   printf("Square root of %lf is %lf\n", 225.0, sqrt(225.0) );
   printf("Square root of %lf is %lf\n", 300.0, sqrt(300.0) );

   return(0);
}
```

输出:

```cpp
Square root of 225.000000 is 15.000000
Square root of 300.000000 is 17.320508
```

8.**双幂(双 x，双 y)**:C 库函数双幂(双 x，双 y)返回 x 升到 y 的幂，即 xy。

```cpp
syntax : double pow(double x, double y)
```

## C

```cpp
// C code to illustrate
// the use of pow function
#include <stdio.h>
#include <math.h>

int main ()
{
   printf("Value 8.0 ^ 3 = %lf\n", pow(8.0, 3));

   printf("Value 3.05 ^ 1.98 = %lf", pow(3.05, 1.98));

   return(0);
}
```

输出:

```cpp
Value 8.0 ^ 3 = 512.000000
Value 3.05 ^ 1.98 = 9.097324
```

9. **double modf(double x，double *integer)**:C 库函数 double modf(double x，double * integer)返回分数分量(小数后的部分)，将 integer 设置为整数分量。

```cpp
syntax : double modf(double x, double *integer)
```

## C

```cpp
// C code to illustrate
// the use of modf function
#include<stdio.h>
#include<math.h>

int main ()
{
   double x, fractpart, intpart;

   x = 8.123456;
   fractpart = modf(x, &intpart);

   printf("Integral part = %lf\n", intpart);
   printf("Fraction Part = %lf \n", fractpart);

   return(0);
}
```

输出:

```cpp
Integral part = 8.000000
Fraction Part = 0.123456 
```

10.**double exp(double x)**:C 库函数 double exp(double x)返回 e 的升至 xth 次方的值。

```cpp
syntax : double exp(double x)
```

以下代码代表

## C

```cpp
// C code to illustrate
// the use of exp function
#include <stdio.h>
#include <math.h>

int main ()
{
   double x = 0;

   printf("The exponential value of %lf is %lf\n", x, exp(x));
   printf("The exponential value of %lf is %lf\n", x+1, exp(x+1));
   printf("The exponential value of %lf is %lf\n", x+2, exp(x+2));

   return(0);
}
```

输出:

```cpp
The exponential value of 0.000000 is 1.000000
The exponential value of 1.000000 is 2.718282
The exponential value of 2.000000 is 7.389056
```

11.**double cos(double x)**:C 库函数 double cos(double x)返回一个弧度角 x 的余弦值。

```cpp
syntax : double cos(double x) 
```

**注:**同样的语法可以用于其他三角函数，如 sin、tan 等。

## C

```cpp
// C code to illustrate
// the use of cos function
#include <stdio.h>
#include <math.h>

#define PI 3.14159265

int main ()
{
   double x, ret, val;

   x = 60.0;
   val = PI / 180.0;
   ret = cos( x*val );
   printf("The cosine of %lf is %lf degrees\n", x, ret);

   x = 90.0;
   val = PI / 180.0;
   ret = cos( x*val );
   printf("The cosine of %lf is %lf degrees\n", x, ret);

   return(0);
}
```

输出:

```cpp
The cosine of 60.000000 is 0.500000 degrees
The cosine of 90.000000 is 0.000000 degrees
```

12.**double acos(double x):**C 库函数 double acos(double x)以弧度为单位返回 x 的弧余弦。

```cpp
syntax : double acos(double x)
```

**注意:**同样的语法可以用于其他弧三角函数，如 asin、atan 等。

## C

```cpp
// C code to illustrate
// the use of acos function
#include <stdio.h>
#include <math.h>

#define PI 3.14159265

int main ()
{
   double x, ret, val;

   x = 0.9;
   val = 180.0 / PI;

   ret = acos(x) * val;
   printf("The arc cosine of %lf is %lf degrees", x, ret);

   return(0);
}
```

输出:

```cpp
The arc cosine of 0.900000 is 25.855040 degrees
```

13.**double tanh(double x):**C 库函数 double tanh(double x)返回 x 的双曲正切值。

```cpp
syntax : double tanh(double x) 
```

**注:**同样的语法可以用于 sinh、cosh 等其他双曲三角函数。

## C

```cpp
// C code to illustrate
// the use of tanh function
#include <stdio.h>
#include <math.h>

int main ()
{
   double x, ret;
   x = 0.5;

   ret = tanh(x);
   printf("The hyperbolic tangent of %lf is %lf degrees", x, ret);

   return(0);
}
```

输出:

```cpp
The hyperbolic tangent of 0.500000 is 0.462117 degrees
```

本文由**阿维纳什库马尔辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。