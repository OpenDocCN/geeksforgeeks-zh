# C 中的格式说明符

> 原文:[https://www.geeksforgeeks.org/format-specifiers-in-c/](https://www.geeksforgeeks.org/format-specifiers-in-c/)

格式说明符在输入和输出期间使用。在使用 scanf()进行输入或使用 printf()进行打印的过程中，这是一种告诉编译器变量中数据类型的方法。一些例子是%c、%d、%f 等。
printf()和 scanf()中的格式说明符大部分是相同的，但是有一些区别，我们将会看到。

### printf(char *format、arg1、arg2、…)

此函数在标准输出上打印字符，并返回打印的字符数。格式是以 **%** 开头，以转换字符(如 c、I、f、d 等)结尾的字符串。).
在两者之间，可以有控制打印格式的元素。以下是它的描述

1.  减号(-)表示左对齐。
2.  **%** 后的数字指定如果字符小于宽度的大小，剩余的空间用空格填充，如果大于，则不截断打印。
3.  句号(。)符号用精度分隔字段宽度。

精度表示整数中的最小位数、字符串中的最大字符数以及浮点值中小数部分之后的位数。让我们看看这些..
**字符格式说明符:%c**

## C

```cpp
#include <stdio.h>
int main()
{
    char ch = 'A';
    printf("%c\n", ch);
    return 0;
}
```

**Output:** 

```cpp
A
```