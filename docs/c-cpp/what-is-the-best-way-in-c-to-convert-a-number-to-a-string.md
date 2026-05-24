# C 语言中把数字转换成字符串的最好方法是什么？

> 原文:[https://www . geesforgeks . org/c-to-convert-a-number-to-string 的最佳方式是什么/](https://www.geeksforgeeks.org/what-is-the-best-way-in-c-to-convert-a-number-to-a-string/)

**解决方法:**使用 sprintf()函数。

```cpp
#include<stdio.h>
int main()
{
    char result[50];
    float num = 23.34;
    sprintf(result, "%f", num);
    printf("\n The string for the num is %s", result);
    getchar();
}
```

您也可以使用数字的 ASCII 值编写自己的函数。