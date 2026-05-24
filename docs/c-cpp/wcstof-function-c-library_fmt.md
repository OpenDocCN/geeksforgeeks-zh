# C 库中 wcstof 函数

> 原文：[https://www.geeksforgeeks.org/wcstof-function-c-library/](https://www.geeksforgeeks.org/wcstof-function-c-library/)

`wcstof()`函数将`str`指向的宽字符串的初始部分转换为浮点值。`str`参数指向可以解释为数字浮点值的字符序列。这些函数在第一个不能识别为数字一部分的字符处停止读取字符串，即如果第一个字符是除数字之外的任何类型的字符，则函数仅在此处终止。该字符可以是字符串末尾的`wchar_t`空字符。

以‘wcs’开头的标准库函数在 C 的`wchar.h`库中声明。

**语法：**

```cpp
float wcstof (const wchar_t* str, wchar_t** endptr);
```

**Parameters：**

- `str`：C 宽字符串，以浮点数的表示形式开始。
- `endptr`：对已分配的`wchar_t*`类型对象的引用，其值由函数设置为`str`中数值之后的下一个字符。此参数也可以是一个空指针。

**Return value：** 成功时返回与`str`内容对应的浮点值。如果转换值超出相应返回类型的范围，则会发生范围错误并返回。

## C

```cpp
// C code to convert string having
// floating point as its content
// using wcstof function

#include <stdio.h>

// header file containing wcstof function
#include <wchar.h>

int main()
{
    // wide Character array to be parsed
    wchar_t str[] = L"58.152 9.26";

    // Wide Character array to be parsed
    wchar_t* pEnd;

    // float variable to store floating point values
    float f1, f2;

    // Parsing the float values to f1 and f2
    f1 = wcstof(str, &pEnd);
    f2 = wcstof(pEnd, NULL);
    f2 = 2 * f2;

    // Printing parsed float values of f1 and f2
    wprintf(L"%.2f\n%.2f\n", f1, f2);

    // operation being performed on the values parsed
    wprintf(L"Value of Pie is %.2f .\n", f1 / f2);

    return 0;
}
```

**输出：**

```cpp
58.15
18.52
Value of Pie is 3.14 .
```