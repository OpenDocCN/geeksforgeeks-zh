# 如何在 C 中动态分配一个 2D 数组？

> 原文:[https://www . geeksforgeeks . org/dynamic-allocate-2d-array-c/](https://www.geeksforgeeks.org/dynamically-allocate-2d-array-c/)

以下是在堆上创建 2D 数组(或动态分配 2D 数组)的不同方法。
在下面的例子中，我们考虑了作为行数的“ **r** ”，作为列数的“ **c** ，我们创建了 r = 3，c = 4 和以下值的 2D 数组

```cpp
  1  2  3  4
  5  6  7  8
  9  10 11 12 
```

**1)使用单个指针和带有指针算法的 1D 数组:**
一种简单的方法是分配大小为 r*c 的内存块，并使用简单的指针算法访问其元素。

## C

```cpp
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
    int r = 3, c = 4;

    int* ptr = malloc((r * c) * sizeof(int));

    /* Putting 1 to 12 in the 1D array in a sequence */
    for (int i = 0; i < r * c; i++)
        ptr[i] = i + 1;

    /* Accessing the array values as if it was a 2D array */
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++)
            printf("%d ", ptr[i * c + j]);
        printf("\n");
    }

    free(ptr);

    return 0;
}
```

输出:

```cpp
1 2 3 4
5 6 7 8
9 10 11 12
```

**2)使用指针数组**
我们可以创建一个大小为 r 的指针数组，注意从 C99 开始，C 语言允许可变大小的数组。创建指针数组后，我们可以为每一行动态分配内存。

## C

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int r = 3, c = 4, i, j, count;

    int* arr[r];
    for (i = 0; i < r; i++)
        arr[i] = (int*)malloc(c * sizeof(int));

    // Note that arr[i][j] is same as *(*(arr+i)+j)
    count = 0;
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            arr[i][j] = ++ count; // Or *(*(arr+i)+j) = ++ count

    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            printf("%d ", arr[i][j]);

    /* Code for further processing and free the
      dynamically allocated memory */

    for (int i = 0; i < r; i++)
        free(arr[i]);

    return 0;
}
```

输出:

```cpp
1 2 3 4 5 6 7 8 9 10 11 12
```

**3)使用指针指向一个指针**
我们也可以使用双指针动态创建一个指针数组。一旦我们有了动态分配的数组指针，我们就可以像方法 2 一样为每一行动态分配内存。

## C

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int r = 3, c = 4, i, j, count;

    int** arr = (int**)malloc(r * sizeof(int*));
    for (i = 0; i < r; i++)
        arr[i] = (int*)malloc(c * sizeof(int));

    // Note that arr[i][j] is same as *(*(arr+i)+j)
    count = 0;
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            arr[i][j] = ++ count; // OR *(*(arr+i)+j) = ++ count

    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            printf("%d ", arr[i][j]);

    /* Code for further processing and free the
       dynamically allocated memory */

    for (int i = 0; i < r; i++)
        free(arr[i]);

    free(arr);

    return 0;
}
```

输出:

```cpp
1 2 3 4 5 6 7 8 9 10 11 12
```

**4)使用双指针和一个 malloc 调用**

## C

```cpp
#include<stdio.h>
#include<stdlib.h>

int main()
{
    int r=3, c=4, len=0;
    int *ptr, **arr;
    int count = 0,i,j;

    len = sizeof(int *) * r + sizeof(int) * c * r;
    arr = (int **)malloc(len);

    // ptr is now pointing to the first element in of 2D array
    ptr = (int *)(arr + r);

    // for loop to point rows pointer to appropriate location in 2D array
    for(i = 0; i < r; i++)
        arr[i] = (ptr + c * i);

    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            arr[i][j] = ++ count; // OR *(*(arr+i)+j) = ++ count

    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            printf("%d ", arr[i][j]);

    return 0;
}
```

输出:

```cpp
1 2 3 4 5 6 7 8 9 10 11 12
```

感谢 [Trishansh Bhardwaj](https://disqus.com/by/itrishansh/) 提出这第四种方法。
本文由**阿沛·拉提**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论

**5)使用指向可变长度数组的指针。**

VLA 的维数与变量的类型有关。因此，可以形成指向具有运行时定义形状的数组的指针。
在用语法(*arr)[i][j]进行下标之前，必须取消指针的引用。

## C

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int r = 3, c = 4, i, j, count;

    int (*arr)[r] = malloc(sizeof *arr);

    count = 0;
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            (*arr)[i][j] = ++ count;

    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            printf("%d ", (*arr)[i][j]);

    free(arr);

    return 0;
}
```

**6)使用指针指向 VLA 的第一行**

类似于 5，但允许 arr[i][j]语法。

## C

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int r = 3, c = 4, i, j, count;

    int (*arr) = calloc(r, sizeof *arr);

    count = 0;
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            arr[i][j] = ++ count;

    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            printf("%d ", arr[i][j]);

    free(arr);

    return 0;
}
```