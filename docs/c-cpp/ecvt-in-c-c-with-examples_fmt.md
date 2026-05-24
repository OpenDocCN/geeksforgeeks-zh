# C/C++ 中的 ecvt() 示例

> 原文：[https://www.geeksforgeeks.org/ecvt-in-c-c-with-examples/](https://www.geeksforgeeks.org/ecvt-in-c-c-with-examples/)

`ecvt()` 函数将 `double` 值转换为字符串，并返回一个指向该字符串的指针。它是一个在 `<stdlib.h>` 头文件中定义的库函数。

## 语法

```c
char *ecvt(double value, int num, int *dec, int *sign);
```

## 参数

*   `double value`：将要转换为字符串的双精度浮点值。
*   `int num`：函数要返回的位数。
*   `int *dec`：一个整数指针，用于存储小数点相对于字符串开头的位置。
*   `int *sign`：一个整数指针，用于接收符号指示，例如 **0** 表示正号，非零表示负号。

该函数返回一个以 null 结尾的字符串，其长度与指定的 `num` 相同，该字符串包含作为参数传递的双精度数的位数。

## 示例

下面的程序说明了 `ecvt()` 函数的使用：

```cpp
// C program to illustrate the
// use of ecvt() function
#include <stdio.h>
#include <stdlib.h>

// Function to illustrate the
// use of ecvt() function
void useOfEcvt()
{
    double x = 123.4567;
    char* buf;
    int dec, sign;

    // Function Call
    buf = ecvt(x, 6, &dec, &sign);

    // Print the converted string
    printf("The converted string "
           "value is: %c%c.%sX10^%d\n",
           sign == 0 ? '+' : '-', '0', buf, dec);
}

// Driver Code
int main()
{
    // Function Call
    useOfEcvt();

    return 0;
}
```

**输出：**

```
The converted string value is: +0.123457X10^3
```

**说明：** 在上述 C 程序中，双精度（浮点）值 `123.4567` 使用 `ecvt()` 函数转换为字符串值 `+0.123457X10^3`。