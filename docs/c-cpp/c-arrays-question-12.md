# C |数组|问题 12

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-12/](https://www.geeksforgeeks.org/c-arrays-question-12/)

```cpp
#include <stdio.h>

int main()
{
    int a[][] = {{1,2},{3,4}};
    int i, j;
    for (i = 0; i < 2; i++)
        for (j = 0; j < 2; j++)
            printf("%d ", a[i][j]);
    return 0;
}
```

**(A)** 1 2 3 4
**(B)** 第“int a[][] = {{1，2}，{3，4}}”行出现编译器错误
**(C)** 4 垃圾值
**(D)**4 3 2 1

**回答:****(B)**

**说明:**声明“int a[][] = {{1，2}，{3，4}}”存在编译错误。

除了第一个维度，必须指定所有其他维度。

int arr[] = {5，6，7，8 }//有效

int arr[][5]= { }；//有效

int arr[][]= { }；//无效

int arr[][10][5]= { }；//有效

int arr[][][5]= { }；//无效

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)