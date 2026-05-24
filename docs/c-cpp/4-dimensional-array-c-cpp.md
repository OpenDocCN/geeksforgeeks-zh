# C/c++ 中的四维数组

> 原文:[https://www.geeksforgeeks.org/4-dimensional-array-c-cpp/](https://www.geeksforgeeks.org/4-dimensional-array-c-cpp/)

先决条件:[C/c++ ](https://www.geeksforgeeks.org/arrays-in-c-language-set-1-introduction/)中的数组，[更多关于数组](https://www.geeksforgeeks.org/arrays-in-c-language-set-2-interesting-array-properties/)

四维(4D)数组是数组的数组，或者换句话说，4D 数组是三维数组的数组。
数组中的维度越多，意味着要容纳的数据越多，但也意味着管理和理解数组的难度越大。

**用 C 语言声明多维数组:**
**语法:**

```cpp
data_type array_name[i1][i2][i3][i4]………[in];
where each i is a dimension, and in is the size of final dimension.
```

例:
1。**int student[4][5][6][7]；**
int 指定数组类型整数。
学生是我们 4D 阵的名字。
我们的数组可以容纳 840 个整型元素。这个数字是通过乘以每个维度的值得出的。在这种情况下:4x5x6x7=840。

2.**浮动国家[5][6][5][6][5]；**
阵国是五维阵。
可以容纳 4500 个浮点元素(5x6x5x6x5=4500)。

**程序:**

```cpp
// C Program to input 4D Matrix and print it.
#include <stdio.h>
int main()
{
    // variable declaration used for indexes
    int i, j, k, l, size;

    // Array declaration
    int a[2][2][2][2];

    // size of array
    size = 2;

    // elements input
    a[0][0][0][0] = 5;
    a[0][0][0][1] = 3;
    a[0][0][1][0] = 5;
    a[0][0][1][1] = 3;
    a[0][1][0][0] = 6;
    a[0][1][0][1] = 7;
    a[0][1][1][0] = 6;
    a[0][1][1][1] = 7;
    a[1][0][0][0] = 8;
    a[1][0][0][1] = 9;
    a[1][0][1][0] = 8;
    a[1][0][1][1] = 9;
    a[1][1][0][0] = 9;
    a[1][1][0][1] = 7;
    a[1][1][1][0] = 9;
    a[1][1][1][1] = 7;

    // Printing the values
    for (i = 0; i < size; i++) {
        for (j = 0; j < size; j++) {
            for (k = 0; k < size; k++) {
                for (l = 0; l < size; l++) {
                    printf("Value of a[%d][%d][%d][%d] :- %d ", 
                                   i, j, k, l, a[i][j][k][l]);
                    printf("\n");
                }
            }
        }
    }
    return 0;
}
```

**Output:**

```cpp
Value of a[0][0][0][0] :- 5 
Value of a[0][0][0][1] :- 3 
Value of a[0][0][1][0] :- 5 
Value of a[0][0][1][1] :- 3 
Value of a[0][1][0][0] :- 6 
Value of a[0][1][0][1] :- 7 
Value of a[0][1][1][0] :- 6 
Value of a[0][1][1][1] :- 7 
Value of a[1][0][0][0] :- 8 
Value of a[1][0][0][1] :- 9 
Value of a[1][0][1][0] :- 8 
Value of a[1][0][1][1] :- 9 
Value of a[1][1][0][0] :- 9 
Value of a[1][1][0][1] :- 7 
Value of a[1][1][1][0] :- 9 
Value of a[1][1][1][1] :- 7

```

**使用:**
一个 4D 数组可以用来存储一组数据，比如我们输入 3 个坐标& 1 次，即 x，y，z，t，我们要检查两车是否有碰撞。