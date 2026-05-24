# 如何避免 C 语言中的结构填充？

> 原文:[https://www . geeksforgeeks . org/如何避免结构填充-in-c/](https://www.geeksforgeeks.org/how-to-avoid-structure-padding-in-c/)

**先决条件:** [结构构件对齐、填充和数据打包](https://www.geeksforgeeks.org/structure-member-alignment-padding-and-data-packing/)

在结构中，由于**结构填充**，有时结构的尺寸大于所有结构构件的尺寸。

下面是结构填充的例子:

```cpp
// C program to show an example
// of Structure padding
#include <stdio.h>

struct s {
    int i;
    char ch;
    double d;
};

int main()
{
    struct s A;
    printf("Size of A is: %ld", sizeof(A));
}
```

**输出:**

```cpp
Size of A is: 16

```