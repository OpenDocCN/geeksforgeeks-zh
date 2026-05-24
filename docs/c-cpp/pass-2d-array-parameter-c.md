# 如何在 C 语言中传递一个 2D 数组作为参数？

> 原文:[https://www.geeksforgeeks.org/pass-2d-array-parameter-c/](https://www.geeksforgeeks.org/pass-2d-array-parameter-c/)

本文是[的扩展如何在 C 中动态分配一个 2D 数组？](https://www.geeksforgeeks.org/dynamically-allocate-2d-array-c/)
一维数组可以很容易地作为指针传递，但是将 2D 数组传递给函数的语法可能很难记住。传递多维数组的一个重要事项是，不必指定第一个数组维度。第二个(以及任何后续的)维度必须给出
**1)当两个维度都是全局可用的(作为一个宏或作为一个全局常数)。**

## C

```cpp
#include <stdio.h>
const int M = 3;
const int N = 3;

void print(int arr[M][N])
{
    int i, j;
    for (i = 0; i < M; i++)
      for (j = 0; j < N; j++)
        printf("%d ", arr[i][j]);
}

int main()
{
    int arr[][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    print(arr);
    return 0;
}
```

**Output**

```cpp
1 2 3 4 5 6 7 8 9 
```

**2)当只有第二维全局可用时(作为宏或全局常数)。**

## C

```cpp
#include <stdio.h>
const int N = 3;

void print(int arr[][N], int m)
{
    int i, j;
    for (i = 0; i < m; i++)
      for (j = 0; j < N; j++)
        printf("%d ", arr[i][j]);
}

int main()
{
    int arr[][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    print(arr, 3);
    return 0;
}
```

**Output**

```cpp
1 2 3 4 5 6 7 8 9 
```