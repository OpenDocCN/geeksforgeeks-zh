# 是 C 语言中的 xdigit()函数

> 原文:[https://www.geeksforgeeks.org/isxdigit-function-c-language/](https://www.geeksforgeeks.org/isxdigit-function-c-language/)

C 编程语言中的 isxdigit()函数，检查给定字符是否为十六进制。函数是在 ctype.h 头文件中定义的。

**十进制数的十六进制等价物:**

```cpp
Hexadecimal: 0   1   2   3    4   5    6   7    8   9    A    B       C      D    E     F
Decimal:    0   1    2   3    4   5    6   7    8   9    10   11    12     13    14    15

```

**语法:**

```cpp
char isxdigit( char x);

```

```cpp
Input : A
Output : Entered character is hexadecimal
Input : 2
Output : Entered character is hexadecimal
Input : @
Output : Entered character is not hexadecimal

```

```cpp
// C program to demonstrate isxdigit()
#include <ctype.h>
#include <stdio.h>

int main()
{
    // taking input
    char ch = 'A';

    // checking is the given input is hexadecimal or not?
    if (isxdigit(ch))
        printf("\nEntered character is hexadecimal");
    else
        printf("\nEntered character is not hexadecimal");
}
```

输出:

```cpp
Entered character is hexadecimal

```

**应用:**C 编程语言中的 isxdigit()函数用于找出任意给定输入中出现的十六进制数的总数。
T3】例:

```cpp
Input: abc123
Output: Number of hexadecimals present in the given input is : 6
Input: abcdef
Output: Number of hexadecimals present in the given input is : 6
Input: 123456@$
Output: Number of hexadecimals present in the given input is : 6

```

让我们来看看 C 程序关于这个话题:

```cpp
// C program to demonstrate isxdigit()
#include <ctype.h>
#include <stdio.h>

int ttl_hexadecimal(int i, int counter)
{
    char ch;
    char a[50] = "@#asf12345";
    ch = a[0];

    // counting of hexadecimal numbers
    while (ch != '\0') {
        ch = a[i];
        if (isxdigit(ch))
            counter++ ;

        i++ ;
    }

    // returning total number of hexadecimal
    // in the given input
    return (counter);
}

int main()
{
    int i = 0;
    int counter = 0;
    counter = ttl_hexadecimal(i, counter);

    printf("\nNumber of hexadecimals in string"
             " is : %d", counter);
    return 0;
}
```

输出:

```cpp
Number of hexadecimals in string is : 7
```