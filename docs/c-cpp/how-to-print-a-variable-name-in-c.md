# 如何用 C 语言打印变量名？

> 原文:[https://www . geesforgeks . org/如何打印 c 语言中的变量名/](https://www.geeksforgeeks.org/how-to-print-a-variable-name-in-c/)

如何在字符串变量中打印和存储变量名？

**我们强烈建议您最小化浏览器，先自己尝试一下**

在 C 语言中，有一个#指令，也叫做‘Stringizing Operator’，它具有这种魔力。基本上#指令将其参数转换为字符串。

```cpp
#include <stdio.h>
#define getName(var)  #var

int main()
{
    int myVar;
    printf("%s", getName(myVar));
    return 0;
} 
```

**输出:**

```cpp
myVar

```