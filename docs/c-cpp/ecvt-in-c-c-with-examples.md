# C/c++ 中的 ecvt()，示例

> 原文:[https://www.geeksforgeeks.org/ecvt-in-c-c-with-examples/](https://www.geeksforgeeks.org/ecvt-in-c-c-with-examples/)

此功能 **ecvt()** 将[双](https://www.geeksforgeeks.org/difference-float-double-c-cpp/)值转换为[字符串](https://www.geeksforgeeks.org/string-data-structure/)值，并返回一个[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)给它。在 [**stdlib.h**](https://www.geeksforgeeks.org/whats-difference-between-and/) [头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)中定义的库函数。

**语法:**

> char * ecvt(双值，int num，int * dec，int *符号)；

**参数:**

*   **双值:**是将转换为字符串的双值。
*   **int num:** 是函数要返回的位数。
*   **int * dec:** 是整数指针，存储相对于字符串开头的小数点位置。
*   **int *符号:**为整数指针，接收符号指示，如 **0** 表示正符号，非零表示负符号。

该函数返回一个以 null 结尾的字符串，其长度与指定的 **num** 相同，该字符串包含作为参数传递的双数位数。

下面是程序说明使用 **ecvt()** 功能:

T5】CT7

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

T8T10**输出:**T1

**说明:**在上述 C 程序中，双(浮点)值即 **123.4567** 使用 **ecvt()** 功能转换为字符串值(+ 0.123457X10 <sup>3</sup> )。