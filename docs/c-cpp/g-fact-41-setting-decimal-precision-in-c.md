# 设置 C 中的小数精度

> 原文:[https://www . geesforgeks . org/g-fact-41-setting-decimal-precision-in-c/](https://www.geeksforgeeks.org/g-fact-41-setting-decimal-precision-in-c/)

如何打印指定精度的浮点数？不需要舍入。例如，如果给定的精度为 4，则应将 5.48958123 打印为 5.4895。

例如，下面的程序设置小数点后 4 位的精度:

```cpp
// C program to set precision in floating point numbers
#include<stdio.h>
#include<math.h>
int main()
{
   float num = 5.48958123;

   // 4 digits after the decimal point
   num = floor(10000*num)/10000;

   printf("%f", num);
   return 0;
}
```

输出:

```cpp
5.489500
```

我们可以使用 pow()来推广上面的方法

```cpp
float newPrecision(float n, float i)
{
    return floor(pow(10,i)*n)/pow(10,i);
}
```

 ***在 C 中，C 中有一个格式说明符，要打印点后 4 位数字，我们可以在 printf()中使用 0.4f。下面是程序演示同样的**。*

```cpp
// C program to set precision in floating point numbers
// using format specifier
#include<stdio.h>

int main() 
{
    float num = 5.48958123;

    // 4 digits after the decimal point  
    printf("%0.4f", num); 
    return 0;
}
```

输出:

```cpp
5.4896
```

本文由 **Niharika Khandelwal** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论