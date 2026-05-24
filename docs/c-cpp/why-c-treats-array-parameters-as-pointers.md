# 为什么 C 把数组参数当成指针？

> 原文:[https://www . geesforgeks . org/why-c-treats-array-parameters-as-pointers/](https://www.geeksforgeeks.org/why-c-treats-array-parameters-as-pointers/)

在 C 语言中，数组参数主要作为指针来处理，

*   To **increase the efficiency of the code**
*   Save time by

从内存和时间两方面来看，复制阵列数据都是低效的；大多数时候，当我们传递一个数组时，我们的意图只是引用我们感兴趣的数组，而不是创建数组的副本。

fun()的以下两个定义看起来不同，但对编译器来说，它们的意思完全相同。

```cpp
void fun(int arr[]) { 
    // body
}
// This is valid

void fun(int *arr) { 
    // body
}
// This is valid too
```

为了可读性，最好使用更准确的语法。

> **注意:**如果进来的指针真的是整个数组的基址，那么我们应该用[ ]。

**示例:**在本例中，数组参数被用作指针。

T5】CT7

```cpp
// C Program to demonstrate that C treats array parameters
// as pointers
#include <stdio.h>

void findSum1(int arr[])
{
    int sum = 0;
    for (int i = 0; i < 5; i++)
        sum = sum + arr[i];
    printf("The sum of the array is: %d\n", sum);
}

void findSum2(int* arr)
{
    int sum = 0;
    for (int i = 0; i < 5; i++)
        sum = sum + arr[i];
    printf("\nThe sum of the array is: %d \n", sum);
}

// Driver code
int main()
{
    int arr[5] = { 1, 2, 3, 4, 5 };

    findSum1(arr);
    findSum2(arr);
    return 0;
}
```

T8T10**输出**T1

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。