# C 程序检查一个数字是正还是负还是零

> 原文: [https://www.geeksforgeeks.org/c-program-to-check-whether-a-number-is-positive-or-negative-or-zero/](https://www.geeksforgeeks.org/c-program-to-check-whether-a-number-is-positive-or-negative-or-zero/)

给定一个数字 `A`。任务是检查 `A` 是正的、负的还是零。

![](img/ac567cb28bbac67d5841535cb08d0da4.png)

**示例**:

```cpp
Input: A = 2
Output: 2 is positive

Input: A = -554
Output: -554 is negative
```

在下面的程序中，查找 `A` 是正、负还是零；首先使用 `scanf` 从用户处获取数字作为输入，然后使用 `if-else` 语句和 `>`、`<` 和 `==` 运算符检查 `A` 是否为正。

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