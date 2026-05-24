# 仅使用 putchar()在 C 中打印长整型

> 原文:[https://www . geesforgeks . org/print-long-int-number-c-using-put char/](https://www.geeksforgeeks.org/print-long-int-number-c-using-putchar/)

编写一个 C 函数 *print(n)* ，以一个长整数 *n* 为参数，在控制台上打印出来。唯一允许的库函数是 *putchar()* ，不允许其他类似 *itoa()* 或 *printf()* 的函数。也不允许使用循环。

***强烈建议尽量减少浏览器，先自己试试这个。**T3】*

这是一个简单的技巧问题。由于 putchar()打印一个字符，我们需要为所有数字调用 putchar()。递归总是可以用来代替迭代，所以使用递归我们可以一个一个地打印所有的数字。现在的问题是 [putchar()](http://www.cplusplus.com/reference/cstdio/putchar/) 打印一个字符，如何使用 putchar()打印数字。我们需要将每个数字转换为其对应的 ASCII 值，这可以通过使用 ASCII 值“0”来完成。下面是完整的 C 程序。

## C

```cpp
/* C program to print a long int number
 using putchar() only*/
#include <stdio.h>

void print(long n)
{
    // If number is smaller than 0, put a - sign
    // and change number to positive
    if (n < 0) {
        putchar('-');
        n = -n;
    }

    // Remove the last digit and recur
    if (n/10)
        print(n/10);

    // Print the last digit
    putchar(n%10 + '0');
}

// Driver program to test above function
int main()
{
    long int n = 12045;
    print(n);
    return 0;
}
```

**输出:**

```cpp
12045
```

需要注意的一点是 putchar()和递归调用 print(n/10)的顺序。由于数字应该从左到右打印，递归调用必须出现在 putchar()之前(最右边的数字应该打印在末尾，所有其他数字必须打印在它之前)。

本文由**阿沛·拉提**供稿。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息