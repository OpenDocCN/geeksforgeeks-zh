# 输入一个 C 中没有空格的整数数组

> 原文:[https://www . geesforgeks . org/input-a-integer-array-不带空格-in-c/](https://www.geeksforgeeks.org/input-an-integer-array-without-spaces-in-c/)

如何输入一个没有空格的大数字(即使在 long long int 中也不能存储的数字)？我们需要整数数组中的这个大数字，以便每个数组元素存储一个位数。

```cpp
Input : 10000000000000000000000000000000000000000000000
We need to read it in an arr[] = {1, 0, 0...., 0}

```

在 C scanf()中，我们可以指定一次读取的位数。这里我们只需要一次读取一个数字，所以我们使用%1d。

```cpp
// C program to read a large number digit by digit
#include <stdio.h>
int main()
{
    // array to store digits
    int a[100000];
    int i, number_of_digits;
    scanf("%d", &number_of_digits);
    for (i = 0; i < number_of_digits; i++) {

        // %1d reads a single digit
        scanf("%1d", &a[i]);
    }

    for (i = 0; i < number_of_digits; i++) 
        printf("%d ", a[i]);

    return 0;
}
```

输入:

```cpp
27
123456789123456789123456789

```

输出:

```cpp
1 2 3 4 5 6 7 8 9 1 2 3 4 5 6 7 8 9 1 2 3 4 5 6 7 8 9 

```

我们也可以使用上面的样式来读取任意数量的固定数字。例如，下面的代码读取一个 3 位数的大数字组。

```cpp
// C program to read a large number digit by digit
#include <stdio.h>
int main()
{
    // array to store digits
    int a[100000];
    int i, count;
    scanf("%d", &count);
    for (i = 0; i < count; i++) {

        // %1d reads a single digit
        scanf("%3d", &a[i]);
    }

    for (i = 0; i < count; i++) 
        printf("%d ", a[i]);

    return 0;
}
```

输入:

```cpp
9
123456789123456789123456789

```

输出:

```cpp
123 456 789 123 456 789 123 456 789 

```

当我们使用 **fscanf()** 读取文件时，也可以使用相同的概念