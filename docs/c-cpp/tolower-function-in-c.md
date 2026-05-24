# 在 C

中关闭()功能

> 原文:[https://www.geeksforgeeks.org/tolower-function-in-c/](https://www.geeksforgeeks.org/tolower-function-in-c/)

**tolower()** 函数在 **ctype.h** 头文件中定义。如果传递的字符是大写字母，那么 tolower()函数会将大写字母转换为小写字母。
**语法:**

```cpp
int tolower(int ch);
```

**参数:**该方法取一个必输参数 **ch** ，即要转换为小写的字符。
**返回值:**该函数返回 ch 对应的**小写字符**。
以下程序说明了 C 语言中的 tolower()函数:
**示例 1:-**

## c

```cpp
// C program to demonstrate
// example of tolower() function.

#include <ctype.h>
#include <stdio.h>

int main()
{

    // Character to be converted to lowercase
    char ch = 'G';

    // convert ch to lowercase using toLower()
    printf("%c in lowercase is represented as = %c", ch, tolower(ch));

    return 0;
}
```

**Output:** 

```cpp
G in lowercase is represented as = g
```

**例 2:-**

## c

```cpp
// C program to demonstrate
// example of tolower() function.

#include <ctype.h>
#include <stdio.h>

int main()
{
    int j = 0;
    char str[] = "GEEKSFORGEEKS\n";

    // Character to be converted to lowercase
    char ch = 'G';

    // convert ch to lowercase using toLower()
    char ch;

    while (str[j]) {
        ch = str[j];

        // convert ch to lowercase using toLower()
        putchar(tolower(ch));

        j++ ;
    }

    return 0;
}
```

**Output:** 

```cpp
geeksforgeeks
```

**注:**

如果在 tolower()中传递的字符是这三个字符中的任何一个

1.小写字符

2.特殊符号

3.手指

tolower()将按原样返回字符。

**示例:**

## C

```cpp
// C program to demonstrate
// example of tolower() function.
#include <ctype.h>
#include <stdio.h>

int main()
{
    int j = 0;
    char str[] = "GeEks@123\n";
    char ch;

    while (str[j]) {
        ch = str[j];
        putchar(tolower(ch));
        j++ ;
    }

    return 0;
}
// code is contributed by codersaty
```

**Output**

```cpp
geeks@123

```