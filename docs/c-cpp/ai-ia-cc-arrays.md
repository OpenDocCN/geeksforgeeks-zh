# 为什么 C/C++ 数组中的 a[i] == i[a]？

> 原文:[https://www.geeksforgeeks.org/ai-ia-cc-arrays/](https://www.geeksforgeeks.org/ai-ia-cc-arrays/)

C 中[]下标运算符运算符的定义，根据(C99，6.5.2.1p2)，是

```cpp
 E1[E2] is identical to (*((E1)+(E2)))
```

编译器在内部使用指针算法来访问数组元素。由于适用于二进制+运算符的转换规则，如果 E1 是一个数组对象(相当于指向数组对象初始元素的指针)，而 E2 是一个整数，则 E1[E2]指定 E1 的第 E2 个元素(从零开始计数)。

因此**a【b】**定义为:

```cpp
a[b] == *(a + b)

```

所以**会评估为**

```cpp
**a[8] == *(a + 8)** 
```

**这里，a 是指向数组第一个元素的指针，a[8]是距离 a 更远的 8 个元素的值，这与*(a + 8)相同，并且 **8[a]** 将计算出以下值，这意味着两者相同。**

```cpp
**8[a] == *(8 + a)** 
```

**所以通过加法[交换性质](https://en.wikipedia.org/wiki/Commutative_property)， **a[8] == 8[a]****

**显示上述结果的示例程序:**

```cpp
// C program to illustrate
// a[i] == i[a] in arrays 
#include <stdio.h>
int main()
{
    int a[] = {1, 2, 3, 4, 5, 6, 7};
    printf("a[5] is %d\n", a[5]);
    printf("5[a] is %d\n", 5[a]);
    return 0;
}
```

**输出:**

```cpp
a[5] is 6
5[a] is 6 
```

**本文由 [**曼德普·辛格**](https://github.com/msdeep14) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**