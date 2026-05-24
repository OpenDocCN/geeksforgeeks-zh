# C |指针基础|问题 4

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-4/](https://www.geeksforgeeks.org/c-pointers-question-4/)

考虑一个编译器，其中 int 取 4 字节，char 取 1 字节，指针取 4 字节。

```cpp
#include <stdio.h>

int main()
{
    int arri[] = {1, 2 ,3};
    int *ptri = arri;

    char arrc[] = {1, 2 ,3};
    char *ptrc = arrc;

    printf("sizeof arri[] = %d ", sizeof(arri));
    printf("sizeof ptri = %d ", sizeof(ptri));

    printf("sizeof arrc[] = %d ", sizeof(arrc));
    printf("sizeof ptrc = %d ", sizeof(ptrc));

    return 0;
}
```

**(A)**sizeof arri[]= 3
sizeof ptri = 4
sizeof arrc[]= 3
sizeof ptrc = 4
**(B)**sizeof arri[]= 12
sizeof ptri = 4
sizeof arrc[]= 3
sizeof ptrc = 1
**(C)**sizeof arri[]= 3
sizeof ptri = 4【4】 = 12
sizeof ptri = 4
sizeof arrc[]= 3
sizeof ptrc = 4

**答案:****(D)**

**解释:**数组的大小是元素的个数乘以元素的类型，这就是为什么我们得到 sizeof arri 为 12，sizeof arrc 为 3。 对于编译器来说，指针的大小是固定的。对于编译器来说，所有指针类型占用相同的字节数。这就是为什么 ptri 和 ptrc 都是 4。