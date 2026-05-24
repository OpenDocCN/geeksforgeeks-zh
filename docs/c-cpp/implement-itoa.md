# 实现自己的 itoa()

> 原文:[https://www.geeksforgeeks.org/implement-itoa/](https://www.geeksforgeeks.org/implement-itoa/)

[itoa](http://www.cplusplus.com/reference/cstdlib/itoa/) 函数将整数转换为空终止字符串。它也可以转换负数。伊藤忠函数标准定义如下:-

## C

```cpp
char* itoa(int num, char* buffer, int base)
```

第三个参数基指定转换基。例如:-如果 base 是 2，那么它将把整数转换成它的二进制兼容字符串，或者如果 base 是 16，那么它将创建整数的十六进制转换字符串形式。
如果基数为 10 且值为负，则结果字符串前面会有一个减号(-)。对于任何其他基数，值总是被认为是无符号的。
参考:[http://www.cplusplus.com/reference/cstdlib/itoa/?kw=itoa](http://www.cplusplus.com/reference/cstdlib/itoa/)T4**例:**T7】

```cpp
  itoa(1567, str, 10) should return string "1567"
  itoa(-1567, str, 10) should return string "-1567"
  itoa(1567, str, 2) should return string "11000011111"
  itoa(1567, str, 16) should return string "61f"
```

必须处理给定数字的单个数字，并且必须将它们对应的字符放入给定的字符串中。使用给定基数的重复除法，我们得到从最低有效到最高有效的单个数字。但是在输出中，这些数字是以相反的顺序需要的。因此，我们将重复除法后得到的字符串反转并返回。

## C

```cpp
/* A C++ program to implement itoa() */
#include <iostream>
using namespace std;

/* A utility function to reverse a string  */
void reverse(char str[], int length)
{
    int start = 0;
    int end = length -1;
    while (start < end)
    {
        swap(*(str+start), *(str+end));
        start++ ;
        end--;
    }
}

// Implementation of itoa()
char* itoa(int num, char* str, int base)
{
    int i = 0;
    bool isNegative = false;

    /* Handle 0 explicitly, otherwise empty string is printed for 0 */
    if (num == 0)
    {
        str[i++ ] = '0';
        str[i] = '\0';
        return str;
    }

    // In standard itoa(), negative numbers are handled only with
    // base 10\. Otherwise numbers are considered unsigned.
    if (num < 0 && base == 10)
    {
        isNegative = true;
        num = -num;
    }

    // Process individual digits
    while (num != 0)
    {
        int rem = num % base;
        str[i++ ] = (rem > 9)? (rem-10) + 'a' : rem + '0';
        num = num/base;
    }

    // If number is negative, append '-'
    if (isNegative)
        str[i++ ] = '-';

    str[i] = '\0'; // Append string terminator

    // Reverse the string
    reverse(str, i);

    return str;
}

// Driver program to test implementation of itoa()
int main()
{
    char str[100];
    cout << "Base:10 " << itoa(1567, str, 10) << endl;
    cout << "Base:10 " << itoa(-1567, str, 10) << endl;
    cout << "Base:2 " << itoa(1567, str, 2) << endl;
    cout << "Base:8 " << itoa(1567, str, 8) << endl;
    cout << "Base:16 " << itoa(1567, str, 16) << endl;
    return 0;
}
```

输出:

```cpp
Base:10 1567
Base:10 -1567
Base:2 11000011111
Base:8 3037
Base:16 61f
```

本文由 [**内哈·马哈詹**](http://www.linkedin.com/in/mahajanneha/) 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。