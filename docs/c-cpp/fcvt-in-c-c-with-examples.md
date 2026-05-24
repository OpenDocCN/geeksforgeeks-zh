# C/c++ 中的 fcvt()，示例

> 原文:[https://www.geeksforgeeks.org/fcvt-in-c-c-with-examples/](https://www.geeksforgeeks.org/fcvt-in-c-c-with-examples/)

此函数 fcvt()将浮点值转换为以 NULL 结尾的 ASCII 字符串，并返回指向它的指针。在 [stdlib.h 头文件](https://www.geeksforgeeks.org/whats-difference-between-and/)中定义的库函数中定义。

**语法:**

> char * fcvt(双精度值，int num，int * dec，int * sign)；

**参数:**

> **1。双精度值**:将转换为字符串的浮点值。
> T3】2。int num: 这是一个由函数返回的数字。如果值大于位数，则字符串的其余部分用零填充，如果值小于位数，则将低位数字四舍五入。
> **3。int * dec:** 它是一个整数指针，存储相对于字符串开头的小数点位置。如果为零或小于零，表示小数点位于数字
> **4 的左边。int * sign:** 是一个整数指针，接收 0 表示正符号，非零表示负符号这样的符号指示符。

该函数返回一个以 null 结尾的字符串，其长度与指定为 num 的长度相同，该字符串包含作为参数传递的双精度数字的位数。

下面是说明 fcvt()函数使用的 C 程序:

**例 1:**

## C

```cpp
// C program to illustrate the
// use of fcvt() function
#include <stdio.h>
#include <stdlib.h>

// Function to illustrate the
// use of fcvt() function
void useOfFcvt()
{
    double x = 123.4567;
    char* buf;
    int dec, sign;

    // Function Call
    buf = fcvt(x, 6, &dec, &sign);

    // Print the converted string
    printf("The converted string "
           "value is: %c%c.%sX10^%d\n",
           sign == 0 ? '+' : '-',
           '0', buf, dec);
}

// Driver Code
int main()
{
    // Function Call
    useOfFcvt();
    return 0;
}
```

**Output:**

> 转换后的字符串值为:+0.123456700X10^3

**说明:**
在上面的 C 程序中，使用 fcvt()函数将双(浮点)值即 123.4567 转换为字符串值(+ 0.123457X103)。

**例 2:**

## C++

```cpp
// C program to implement
// FCVT() function
#include <stdio.h>
#include <stdlib.h>

// Driver code
int main(void)
{
    char* string;
    double value;
    int Dec, sign;
    int ndig = 10;
    value = -9.876;
    string = fcvt(value, ndig,
                  &Dec, &sign);
    printf("The converted string"
           " value is: %s Dec "
           "is: %d sign is: %d\n",
           string, Dec, sign);
    return 0;
}
```

**Output:**

> 转换后的字符串值为:98760000000 Dec 为:1 符号为:1