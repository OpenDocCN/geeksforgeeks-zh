# C 语言中的 isalnum()函数

> 原文:[https://www.geeksforgeeks.org/isalnum-function-c-language/](https://www.geeksforgeeks.org/isalnum-function-c-language/)

C 编程语言中的 isalnum()函数检查给定的字符是否是字母数字。在 ctype.h 头文件中定义的 isalnum()函数。

字母数字:字母或数字的字符。
**语法:**

```cpp
int isalnum(int x);
```

```cpp
Input : 1
Output : Entered character is alphanumeric
Input : A
Output : Entered character is alphanumeric
Input : &
Output : Entered character is not alphanumeric

```

```cpp
// C code to illustrate isalphanum()
#include <ctype.h>
#include <stdio.h>

int main()
{
    char ch = 'a';

    // checking is it alphanumeric or not?
    if (isalnum(ch))
        printf("\nEntered character is alphanumeric\n");
    else
        printf("\nEntered character is not alphanumeric\n");
}
```

输出:

```cpp
Entered character is alphanumeric

```

**应用:** isalnum()函数用于找出给定句子(或任何输入)中字母数字的个数。
T3】例:

```cpp
Input: abc123@
Output: Number of alphanumerics in the given input is : 6
Input: a@#
Output: Number of alphanumerics in the given input is : 1
Input: ...akl567
Output: Number of alphanumerics in the given input is : 6

```

```cpp
// C code to illustrate isalphanum()
#include <ctype.h>
#include <stdio.h>

int ttl_alphanumeric(int i, int counter)
{
    char ch;
    char a[50] = "www.geeksforgeeks.org";
    ch = a[0];

    // counting of alphanumerics
    while (ch != '\0') {
        ch = a[i];
        if (isalnum(ch))
            counter++ ;

        i++ ;
    }

    // returning total number of alphanumerics
    // present in given input
    return (counter);
}

int main()
{
    int i = 0;

    int counter = 0;
    counter = ttl_alphanumeric(i, counter);

    printf("\nNumber of alphanumerics in the "
           "given input is : %d", counter);
    return 0;
}
```

输出:

```cpp
Number of alphanumerics in the given input is : 19
```