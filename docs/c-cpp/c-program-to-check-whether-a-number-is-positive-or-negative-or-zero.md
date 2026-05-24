# C 程序检查一个数字是正还是负还是零

> 原文:[https://www . geesforgeks . org/c-program-to-check-a-number-是正还是负还是零/](https://www.geeksforgeeks.org/c-program-to-check-whether-a-number-is-positive-or-negative-or-zero/)

给定一个数字 A。任务是检查 A 是正的、负的还是零。

![](img/ac567cb28bbac67d5841535cb08d0da4.png)

**示例**:

```cpp
Input: A = 2
Output: 2 is positive

Input: A = -554
Output: -554 is negative

```

在下面的程序中，查找 A 是正、负还是零；首先使用![A](img/cc10d3b72431cdd6ba563d3cc2a57d7f.png "Rendered by QuickLaTeX.com")中的 scanf 从用户处获取数字作为输入，然后使用![if-else](img/0a0aa6968e9d1698de35dfb12338bea3.png "Rendered by QuickLaTeX.com")语句和![>](img/1a492dd92af98205c89a6348cdbcffd0.png "Rendered by QuickLaTeX.com")、![<](img/d26ec944523d9df05b4ea7f022720cb6.png "Rendered by QuickLaTeX.com")和![==](img/c9f1e73f9468366680c15b7c599ecc49.png "Rendered by QuickLaTeX.com")运算符检查 A 是否为正。

下面是查找一个数字是正数、负数还是零的 C 程序。

```cpp
#include <stdio.h>

int main()
{
    int A;

    printf("Enter the number A: ");
    scanf("%d", &A);

    if (A > 0)
        printf("%d is positive.", A);
    else if (A < 0)
        printf("%d is negative.", A);
    else if (A == 0)
        printf("%d is zero.", A);

    return 0;
}
```

**输出:**

```cpp
Enter the number A =: -54
-54 is negative.

```