# 不使用 strcpy()函数复制字符串的 C 程序

> 原文:[https://www . geesforgeks . org/c-program-copy-string-not-use-strcpy-function/](https://www.geeksforgeeks.org/c-program-copy-string-without-using-strcpy-function/)

我们可以使用内置的 [strcpy()函数](https://www.geeksforgeeks.org/strcpy-in-c-cpp/)将一个字符串复制到另一个字符串，但是在这里，这个程序将一个字符串的内容手动复制到另一个字符串，而不使用 strcpy()函数。

**方法:**这里我们输入一个字符串，然后借助**进行循环**将第一个数组的内容转移到第二个数组。

**错误:**如果目标字符串长度小于源字符串，整个字符串值不会被复制到目标字符串中。
例如，考虑目标字符串长度为 20，源字符串长度为 30。然后，源字符串中只有 20 个字符将被复制到目标中，其余 10 个字符将被截断。

```cpp
// CPP program to copy one string to other
// without using in-built function

#include <stdio.h>
int main()
{
    // s1 is the source( input) string and s2 is the destination string
    char s1[] = "GeeksforGeeks", s2[100], i;

    // Print the string s1
    printf("string s1 : %s\n", s1);

    // Execute loop till null found
    for (i = 0; s1[i] != '\0'; ++ i) {
        // copying the characters by
        // character to str2 from str1
        s2[i] = s1[i];
    }

    s2[i] = '\0';

    // printing the destination string
    printf("String s2 : %s", s2);

    return 0;
}
```

输出:

```cpp
string s1 : GeeksforGeeks
String s2 : GeeksforGeeks

```