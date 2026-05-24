# C 中指定的初始值设定项

> 原文:[https://www.geeksforgeeks.org/designated-initializers-c/](https://www.geeksforgeeks.org/designated-initializers-c/)

标准 C90 要求初始值设定项的元素以固定顺序出现，与正在初始化的数组或结构中的元素顺序相同。
在 ISO C99，你可以以随机顺序给出元素，指定它们所应用的数组索引或结构字段名，GNU C 也允许这作为 C90 模式的扩展。这个扩展没有在 GNU C++ 中实现。
要指定一个**数组索引**，在元素值前写**'【索引】= '或'【索引】'**。例如

```cpp
     int a[6] = {[4] = 29, [2] = 15 }; or
     int a[6] = {[4]29 , [2]15 };
```

相当于

```cpp
     int a[6] = { 0, 0, 15, 0, 29, 0 };
```

```cpp
Note:- The index values must be constant expressions.
```

要将一系列元素初始化为相同的值，请写入**'[第一个…最后一个] =值'**。例如

```cpp
int a[] = {[0 ... 9] = 1, [10 ... 99] = 2, [100] = 3 };
```

来源:[gcc.gnu.org](https://gcc.gnu.org/onlinedocs/gcc/Designated-Inits.html)T2】

## C

```cpp
// C program to demonstrate designated initializers
// with arrays.
#include <stdio.h>
void main(void)
{
    int numbers[100] = {1, 2, 3, [3 ... 9] = 10,
          [10] = 80, 15, [70] = 50, [42] = 400 };

    int i;
    for (i = 0; i < 20; i++)   
        printf("%d ", numbers[i]);

    printf("\n%d ", numbers[70]);
    printf("%d", numbers[42]);
}
```

输出:

```cpp
1 2 3 10 10 10 10 10 10 10 80 15 0 0 0 0 0 0 0 0 
50 400 
```

说明:

*   在本例中，前三个元素分别初始化为 1、2 和 3。
*   第 4 到第 10 个元素的值为 10。
*   然后第 11 个元素被初始化为 80。
*   下一个元素(第 12 个)被初始化为 15。
*   第 70 个元素(第 71 个)初始化为 50，第 42 个元素(第 43 个)初始化为 400。
*   与正常初始化一样，所有未初始化的值都设置为零。

**注:-**

1.  这个初始值设定项不需要按顺序出现。
2.  数组的长度是指定的最大值加 1。

## C

```cpp
// C program to demonstrate designated initializers
// to determine size of array.
#include <stdio.h>

void main(void)
{
    int numbers[] = {1, 2, 3, [10] = 80, 15,
                    [70] = 50, [42] = 400 };
    int n = sizeof(numbers) / sizeof(numbers[0]);
    printf("%d", n);
}
```

输出:

```cpp
71
```

说明:
如果没有给出数组的大小，那么最大的初始化位置决定了数组的大小。
**在** [**结构**](https://www.geeksforgeeks.org/structures-c/) **或** [**并集**](https://www.geeksforgeeks.org/union-c/) **:**
在结构初始值设定项中，用**指定要初始化的字段的名称。fieldname = '或' fieldname:'** 在元素值之前。例如，给定以下结构，

```cpp
     struct point { int x, y; };
```

以下初始化

```cpp
     struct point p = { .y = 2, .x = 3 }; or
     struct point p = { y: 2, x: 3 };
```

相当于

```cpp
     struct point p = { 2, 3 };
```

## C

```cpp
// C program to demonstrate designated
// initializers with structures
#include <stdio.h>
struct Point
{
    int x, y, z;
};

int main()
{

    // Examples of initialization using
    // designated initialization
    struct Point p1 = {.y = 0, .z = 1, .x = 2};
    struct Point p2 = {.x = 20};

    printf("x = %d, y = %d, z = %d\n",
          p1.x, p1.y, p1.z);

    printf("x = %d", p2.x);

    return 0;
}
```

输出:

```cpp
x = 2, y = 0, z = 1
x = 20
```

我们还可以组合数组和结构的指定初始值设定项。

## C

```cpp
// C program to demonstrate designated initializers
// with structures and arrays combined
#include <stdio.h>
void main(void)
{
    struct point { int x, y; };
    struct point pts[5] = { [2].y = 5, [2].x = 6, [0].x = 2 };
    int i;
    for (i = 0; i < 5; i++)   
        printf("%d %d\n", pts[i].x ,pts[i].y);
}
```

输出:

```cpp
2 0
0 0
6 5
0 0
0 0
```

**参考:**T2[https://gcc.gnu.org/onlinedocs/gcc/Designated-Inits.html](https://gcc.gnu.org/onlinedocs/gcc/Designated-Inits.html)T5】