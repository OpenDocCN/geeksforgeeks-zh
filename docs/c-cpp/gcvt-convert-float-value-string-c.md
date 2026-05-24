# gcvt() |将浮点值转换为 C 中的字符串

> 原文:[https://www . geesforgeks . org/gcvt-convert-float-value-string-c/](https://www.geeksforgeeks.org/gcvt-convert-float-value-string-c/)

在这里，我们将看到一个浮点数(浮点值)如何用 C 语言转换成字符串。它是在 stdio.h 头文件中定义的库函数。此函数用于将浮点数转换为字符串。
**语法:**

```cpp
gcvt (float value, int ndigits, char * buf);

float value : It is the float or double value.
int ndigits : It is number of digits.
char * buf : It is character pointer, in this 
variable string converted value will be copied.
```

**示例:**

```cpp
Input : 123.4567
Output :123.457

Input : 12345.6789
Output : 12345.7

```

```cpp
// C program to convert float
// value in string using gcvt()
#include <stdio.h>
#define MAX 100

int main()
{
    float x = 123.4567;
    char buf[MAX];

    gcvt(x, 6, buf);

    printf("buffer is: %s\n", buf);

    return 0;
}
```

输出:

```cpp
buffer is: 123.457
```

**应用:**以下程序显示了当除法结果存储在
浮点类型(结果精度可达小数点后六位)时与直接存储在字符串类型时的输出差异。

```cpp
// C program to illustrate
// application of gcvt()
#include <stdio.h>
// called function
void divide(float x, float y)
{
    char buffer[20];
    float z;
    z = x / y;
    // printing normal division result

    printf("%f", z);
    gcvt(x / y, 10, buffer);

    // printing division result as stored directly in string
    printf("\n%s\n", buffer);
}
int main()
{
    // taking input
    float x = 2.0f, y = 3.0f;

    // calling function for division
    divide(x, y);

    return 0;
}
```

输出:

```cpp
0.666667
0.6666666865

```