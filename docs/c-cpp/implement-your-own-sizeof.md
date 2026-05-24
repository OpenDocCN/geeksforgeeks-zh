# 实现自己的规模

> 原文:[https://www.geeksforgeeks.org/implement-your-own-sizeof/](https://www.geeksforgeeks.org/implement-your-own-sizeof/)

下面是一个实现。

```cpp
#include<stdio.h>
#define my_sizeof(type) (char *)(&type+1)-(char*)(&type)
int main()
{
    double x;
    printf("%ld", my_sizeof(x));
    getchar();
    return 0;
}
```

类型就像宏的局部变量。&type 给出了在程序中声明的变量(double x)的地址，用 1 递增给出了可以存储下一个 x 类型变量的地址(这里 addr_of(x) + 8，因为 double 的大小是 8B)。
这个差给出了这样的结果，x 类型的变量有多少可以存储在这个内存量中，对于 x 类型，这个内存量显然是 1(用 1 来递增它，取这个差就是我们所做的)。将其类型转换为 char*并取其差将告诉我们在给定的内存空间中可以存储多少 char 类型的变量(差)。由于每个字符只需要 1B 内存，因此(内存量)/1 将给出传递给宏的变量类型的两个连续内存位置之间的字节数，从而给出 x 类型变量所需的内存量。
但是您将无法向该宏传递任何文字并知道它们的大小。

您也可以使用函数而不是宏来实现，但是函数实现不能在 C 中完成，因为 C 不支持函数重载，并且 sizeof()应该接收所有数据类型的参数。

注意，上面的实现假设字符的大小是一个字节。

**时间复杂度:**O(1)
T3】空间复杂度: O(1)