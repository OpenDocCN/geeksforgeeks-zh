# 用 C 语言在一个 int 中分配多个字符

> 原文:[https://www . geesforgeks . org/assignment-multi-characters-int-c-language/](https://www.geeksforgeeks.org/assigning-multiple-characters-int-c-language/)

考虑下面的 C 程序。

```cpp
#include <stdio.h>
int main(void)
{
    int a = 'd';

    printf("%d\n", a);
    /*OUTPUT - 100 (ASCII Code for character d)*/

    int b = 'dd';
    printf("%d", b);
    /*OUTPUT - 25700 (Explanation in detail given below)*/

    return 0;
}
```

输出:

```cpp
100
25700

```

我们很容易猜到“d”的输出是 100，因为 100 是字符“d”的 ASCII 值。

让我们考虑线下

```cpp
int a = 'dd' 
```

(%d，a)打印 25700 作为输出
01100100 01100100(100 的二进制数 100)
假设 int 为 2 字节，起始字节由第一个字符“d”占据，第二个字节由第二个字符“d”占据。因此，整体二进制包含 0110010001100100，即 2^14+2^13+2^10+2^6+2^5+2^2 = 25700。

现在猜测以下代码的输出。

```cpp
#include <stdio.h>
int main(void)
{
    int b = 'de';
    printf("%d", b);
    return 0;
}
```