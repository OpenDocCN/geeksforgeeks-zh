# 检查给定字符串是否为关键字的程序

> 原文:[https://www . geesforgeks . org/c-程序检查给定字符串是否为关键字/](https://www.geeksforgeeks.org/c-program-to-check-if-a-given-string-is-keyword-or-not/)

给定一个字符串，任务是编写一个程序，检查给定的字符串是否是[关键字](https://www.geeksforgeeks.org/variables-and-keywords-in-c/)。

*   关键字是不能用作变量名的保留字。
*   C 程序设计语言有 32 个关键词。

**示例:**

```cpp
Input: str = "geeks"
Output: geeks is not a keyword

Input: str = "for"
Output: for is a keyword

```

```cpp
// C program to check whether a given
// string is a keyword or not
#include <stdbool.h>
#include <stdio.h>
#include <string.h>

// Function to check whether the given
// string is a keyword or not
// Returns 'true' if the string is a KEYWORD.
bool isKeyword(char* str)
{
    if (!strcmp(str, "auto") || !strcmp(str, "default") 
        || !strcmp(str, "signed") || !strcmp(str, "enum") 
        ||!strcmp(str, "extern") || !strcmp(str, "for") 
        || !strcmp(str, "register") || !strcmp(str, "if") 
        || !strcmp(str, "else")  || !strcmp(str, "int")
        || !strcmp(str, "while") || !strcmp(str, "do")
        || !strcmp(str, "break") || !strcmp(str, "continue") 
        || !strcmp(str, "double") || !strcmp(str, "float")
        || !strcmp(str, "return") || !strcmp(str, "char")
        || !strcmp(str, "case") || !strcmp(str, "const")
        || !strcmp(str, "sizeof") || !strcmp(str, "long")
        || !strcmp(str, "short") || !strcmp(str, "typedef")
        || !strcmp(str, "switch") || !strcmp(str, "unsigned")
        || !strcmp(str, "void") || !strcmp(str, "static")
        || !strcmp(str, "struct") || !strcmp(str, "goto")
        || !strcmp(str, "union") || !strcmp(str, "volatile"))
        return (true);
    return (false);
}

// Driver code
int main()
{
    isKeyword("geeks") ? printf("Yes\n")
                       : printf("No\n");
    isKeyword("for") ? printf("Yes\n")
                     : printf("No\n");
    return 0;
}
```

**Output:**

```cpp
No
Yes

```