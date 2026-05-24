# C 语言的 isupper()函数

> 原文:[https://www.geeksforgeeks.org/isupper-function-c-language/](https://www.geeksforgeeks.org/isupper-function-c-language/)

C 程序设计中的 isupper()函数检查给定字符是否大写。isupper()函数在 ctype.h 头文件中定义。

**语法:**

```cpp
int isupper ( int x );
```

**示例:**

```cpp
Input: A
Output: Entered character is uppercase character
Input: a
Output: Entered character is not uppercase character
Input: 1
Output: Entered character is not uppercase character
```

## C

```cpp
// C program to demonstrate
// isupper() function
#include <ctype.h>
#include <stdio.h>
int main()
{
    char ch = 'A';

    // checking uppercase
    if (isupper(ch))
        printf("\nEntered character is uppercase character");
    else
        printf("\nEntered character is not uppercase character");
}
```

**输出:**

```cpp
Entered character is uppercase character
```

**应用:**C 编程语言中的 isupper()函数用于找出给定句子中出现的大写字母总数。
T3】例:

```cpp
Input: GEEKSFORGEEKS
Output: Number of upper case present in the sentence is : 13
Input: GeeksFORGeeks
Output: Number of upper case present in the sentence is : 5
Input: geeksforgeeks
Output: Number of upper case present in the sentence is : 0 
```

## C

```cpp
// C program to demonstrate
// isupper() function

#include <ctype.h>
#include <stdio.h>

// called function
int ttl_upper(int i, int counter)
{
    char ch;
    char a[50] = "GeeksForGeeks";
    ch = a[0];

    // counting of upper case
    while (ch != '\0') {
        ch = a[i];
        if (isupper(ch))
            counter++ ;

        i++ ;
    }

    // returning total number of upper case present in sentence
    return (counter);
}
int main()
{
    int i = 0;
    int counter = 0;

    // calling function
    counter = ttl_upper(i, counter);
    printf("\nNumber of upper case present in the sentence is : %d", counter);
    return 0;
}
```

**输出:**

```cpp
Number of upper case present in the sentence is : 3 
```