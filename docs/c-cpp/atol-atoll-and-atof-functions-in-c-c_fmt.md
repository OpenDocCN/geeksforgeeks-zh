# atol()、atoll()和atof()函数在C/C++中

> 原文：[https://www.geeksforgeeks.org/atol-atoll-and-atof-functions-in-c-c/](https://www.geeksforgeeks.org/atol-atoll-and-atof-functions-in-c-c/)

## atol()

此函数将作为参数传递给函数调用的C类型字符串转换为长整型数。它解析C字符串`str`，将其内容解释为整数，并以`long int`类型的值返回。该函数会丢弃字符串开头的空白字符，直到找到非空白字符为止。如果C字符串`str`中的非空白字符序列不是有效的整数，或者由于`str`为空或仅包含空白字符而不存在这样的序列，则不执行转换并返回零。

**语法：**

```cpp
long int atol ( const char * str )
```

**参数：** 该函数接受一个强制参数`str`，它是一个整数的表示。

**返回值：** 函数将转换后的整数作为长整型数返回。如果无法执行有效转换，它将返回零。

```cpp
// CPP program to illustrate
// working of atol() function.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // char array of numbers
    char str1[] = "5672345";

    // Function calling to convert to a long int
    long int num1 = atol(str1);

    cout << "Number is " << num1 << "\n";

    // char array of numbers of spaces
    char str2[] = "10000002  0";

    // Function calling to convert to a long int
    long int num2 = atol(str2);

    cout << "Number is " << num2 << "\n";
    return 0;
}
```

**Output:**

```cpp
Number is 5672345
Number is 10000002
```