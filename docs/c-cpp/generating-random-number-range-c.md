# 在 C

范围内生成随机数

> 原文:[https://www . geesforgeks . org/generating-random-number-range-c/](https://www.geeksforgeeks.org/generating-random-number-range-c/)

如何在 c 语言中生成给定范围内的随机数？

示例:

```cpp
Input : Lower = 50,
        Upper = 100,
        Count of random Number = 5 
Output : 91 34 21 88 29 
Explanation: lower is the lower limit of the 
range and upper is the upper limit of the range.
Output contains 5 random numbers in given range.

```

因为 C 没有生成范围内数字的内置函数，但是它有 [rand 函数](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/)，生成从 0 到 RAND_MAX 的随机数。在 rand()的帮助下，范围内的数字可以生成为 **num = (rand() %(上–下+ 1)) +下**

```cpp
// C program for generating a
// random number in a given range.
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Generates and prints 'count' random
// numbers in range [lower, upper].
void printRandoms(int lower, int upper, 
                             int count)
{
    int i;
    for (i = 0; i < count; i++) {
        int num = (rand() %
           (upper - lower + 1)) + lower;
        printf("%d ", num);
    }
}

// Driver code
int main()
{
    int lower = 5, upper = 7, count = 1;

    // Use current time as 
    // seed for random generator
    srand(time(0));

    printRandoms(lower, upper, count);

    return 0;
}
```

**输出:**

```cpp
7

```

**注意:**每次运行产生的输出可能不同，因为数字是随机产生的。