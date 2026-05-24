# C/c++ 中浮点和双精度的区别

> 原文:[https://www . geesforgeks . org/difference-float-double-c-CPP/](https://www.geeksforgeeks.org/difference-float-double-c-cpp/)

对于表示浮点数，我们使用 **float** 、 **double** 和 **long double** 。

**有什么区别？**

**双**比**浮动**精度高 2 倍。

**float** 是一个 32 位的 IEEE 754 单精度浮点数字 1 位为符号(8 位为指数，23*为数值)，即 float 有 7 位小数精度。

**double** 是一个 64 位的 IEEE 754 双精度浮点数(1 位为符号，11 位为指数，52*位为数值)，即 double 有 15 位小数的精度。

我们举个例子(这里的例子取自):
对于一个二次方程**x2–4.0000000 x+3.9999999 = 0**，10 个有效数字的精确根是，r1 = 2.000316228，r2 = 1.999683772

```cpp
// C program to demonstrate 
// double and float precision values

#include <stdio.h>
#include <math.h>

// utility function which calculate roots of 
// quadratic equation using double values
void double_solve(double a, double b, double c){
    double d = b*b - 4.0*a*c;
    double sd = sqrt(d);
    double r1 = (-b + sd) / (2.0*a);
    double r2 = (-b - sd) / (2.0*a);
    printf("%.5f\t%.5f\n", r1, r2);
}

// utility function which calculate roots of 
// quadratic equation using float values
void float_solve(float a, float b, float c){
    float d = b*b - 4.0f*a*c;
    float sd = sqrtf(d);
    float r1 = (-b + sd) / (2.0f*a);
    float r2 = (-b - sd) / (2.0f*a);
    printf("%.5f\t%.5f\n", r1, r2);
}   

// driver program
int main(){
    float fa = 1.0f;
    float fb = -4.0000000f;
    float fc = 3.9999999f;
    double da = 1.0;
    double db = -4.0000000;
    double dc = 3.9999999;

    printf("roots of equation x2 - 4.0000000 x + 3.9999999 = 0 are : \n");
    printf("for float values: \n");
    float_solve(fa, fb, fc);

    printf("for double values: \n");
    double_solve(da, db, dc);
    return 0;
}  
```

输出:

```cpp
roots of equation x2 - 4.0000000 x + 3.9999999 = 0 are : 
for float values: 
2.00000    2.00000
for double values: 
2.00032    1.99968

```

本文由 **[曼德普·辛格](https://github.com/msdeep14)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。