# 将浮点数转换为 C 语言的字符串

> 原文:[https://www . geesforgeks . org/convert-浮点-数字-字符串/](https://www.geeksforgeeks.org/convert-floating-point-number-string/)

编写一个 C 函数 ftoa()，将给定的浮点数或双精度浮点数转换为字符串。不允许使用标准库函数进行直接转换。以下是 ftoa()的原型。这篇文章提供了将 C double 转换为 string 的见解。

```cpp
ftoa(n, res, afterpoint)
n          --> Input Number
res[]      --> Array where output string to be stored
afterpoint --> Number of digits to be considered after the point.

```

**示例:**

*   ftoa(1.555，str，2)应在 res 中存储“1.55”。
*   ftoa(1.555，str，0)应该在 res 中存储“1”。

 ***我们强烈建议尽量减少浏览器，先自己试试这个。***

一个简单的方法是使用 [sprintf()](https://www.geeksforgeeks.org/what-is-the-best-way-in-c-to-convert-a-number-to-a-string/) ，但是不允许使用标准库函数进行直接转换。

**做法:**思路是将整数部分和小数部分分开，分别转换成字符串。以下是详细步骤。

1.  从浮点数或双数中提取整数部分。
2.  首先，将整数部分转换为字符串。
3.  从 n 中提取整数部分。
4.  如果 d 不为零，则执行以下操作。
    1.  通过将分数部分乘以幂(10，d)将其转换为整数
    2.  将整数值转换为字符串并追加到结果中。

以下是上述方法的 C 实现。

```cpp
// C program for implementation of ftoa()
#include <math.h>
#include <stdio.h>

// Reverses a string 'str' of length 'len'
void reverse(char* str, int len)
{
    int i = 0, j = len - 1, temp;
    while (i < j) {
        temp = str[i];
        str[i] = str[j];
        str[j] = temp;
        i++ ;
        j--;
    }
}

// Converts a given integer x to string str[]. 
// d is the number of digits required in the output. 
// If d is more than the number of digits in x, 
// then 0s are added at the beginning.
int intToStr(int x, char str[], int d)
{
    int i = 0;
    while (x) {
        str[i++ ] = (x % 10) + '0';
        x = x / 10;
    }

    // If number of digits required is more, then
    // add 0s at the beginning
    while (i < d)
        str[i++ ] = '0';

    reverse(str, i);
    str[i] = '\0';
    return i;
}

// Converts a floating-point/double number to a string.
void ftoa(float n, char* res, int afterpoint)
{
    // Extract integer part
    int ipart = (int)n;

    // Extract floating part
    float fpart = n - (float)ipart;

    // convert integer part to string
    int i = intToStr(ipart, res, 0);

    // check for display option after point
    if (afterpoint != 0) {
        res[i] = '.'; // add dot

        // Get the value of fraction part upto given no.
        // of points after dot. The third parameter 
        // is needed to handle cases like 233.007
        fpart = fpart * pow(10, afterpoint);

        intToStr((int)fpart, res + i + 1, afterpoint);
    }
}

// Driver program to test above function
int main()
{
    char res[20];
    float n = 233.007;
    ftoa(n, res, 4);
    printf("\"%s\"\n", res);
    return 0;
}
```

**Output:**

```cpp
"233.0070"

```

**注意:**如果采用双精度类型而不是浮点型，程序将执行类似的操作。

本文由 Jayasantosh Samal 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论