# C/c++

中的 rand()和 srand()

> 原文:[https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/)

**rand ()**

rand()函数在 C/C++ 中用于生成范围为[0，RAND _ MAX 的随机数。

**注意:**如果在没有首先调用 srand()的情况下用 rand()生成随机数，那么您的程序每次运行时都会创建相同的数字序列。

**语法:**

```cpp
 int rand(void): 
returns a pseudo-random number in the range of [0, RAND_MAX).
RAND_MAX: is a constant whose default value may vary 
\between implementations but it is granted to be at least 32767.
```

假设我们在循环中借助 rand()在 C 中生成 5 个随机数，那么每次我们编译和运行程序时，我们的输出一定是相同的数字序列。

## C

```cpp
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
    // This program will create same sequence of
    // random numbers on every program run

    for(int i = 0; i<5; i++)
        printf(" %d ", rand());

    return 0;
}
```

**注意:**该程序将在每次运行时创建相同的随机数序列。
产出 1:

```cpp
453 1276 3425 89
```

产出 2:

```cpp
453 1276 3425 89
```

输出 n:

```cpp
453 1276 3425 89
```

**srand()**

srand()函数设置产生一系列伪随机整数的起点。如果未调用 srand()，则将设置 rand()种子，就像在程序启动时调用 srand(1)一样。种子的任何其他值都会将生成器设置为不同的起点。

**语法:**

```cpp
void srand( unsigned seed ): 
Seeds the pseudo-random number generator used by rand() with the value seed.
```

**注意:**伪随机数发生器应该只植入一次，在对 rand()的任何调用之前，以及程序开始之前。它不应该被重复播种，或者每次你希望生成一批新的伪随机数时都要重新播种。

标准做法是使用调用 **srand(time(0))** 的结果作为种子。但是，time()返回一个 time_t 值，该值每次都不同，因此伪随机数每次程序调用都不同。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C program to generate random numbers
#include <stdio.h>
#include <stdlib.h>
#include<time.h>

// Driver program
int main(void)
{
    // This program will create different sequence of
    // random numbers on every program run

    // Use current time as seed for random generator
    srand(time(0));

    for(int i = 0; i<4; i++)
        printf(" %d ", rand());

    return 0;
}
```

**注意:**这个程序在每次运行时都会产生不同的随机数序列。
产出 1:

```cpp
453 1432 325 89
```

产出 2:

```cpp
8976 21234 45 8975
```

输出 n:

```cpp
563 9873 12321 24132
```

【srand()和 rand()是如何相互关联的？

srand()设置 rand 用来生成“随机”数字的种子。如果在第一次调用 rand 之前没有调用 srand，就好像调用了 srand(1)将种子设置为 1 一样。
简而言之， **srand() —为 rand()函数**设置种子。

本文由[希瓦姆·普拉丹(anuj_charm)](https://www.facebook.com/anuj.charm) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。