# C/c++ 中的 strcat()函数，示例

> 原文:[https://www . geesforgeks . org/strcat-function-in-c-c-with-example/](https://www.geeksforgeeks.org/strcat-function-in-c-c-with-example/)

在 C/C++ 中，strcat()是一个预定义的函数，用于字符串处理，在字符串库( **string.h** 在 C 中， **cstring** 在 C++ 中)下。

该函数将 src 指向的字符串追加到 dest 指向的字符串末尾。它将在目标字符串中附加一个源字符串的副本。加上一个终止的空字符。字符串的初始字符(src)会覆盖字符串末尾的空字符(dest)。

如果出现以下情况，则行为未定义:

*   目标数组对于 src 和 dest 以及终止空字符的内容都不够大
*   如果字符串重叠。
*   如果 dest 或 src 不是指向空终止字节字符串的指针。

**语法:**

```cpp
char *strcat(char *dest, const char *src)
```

**参数:**该方法接受以下参数:

*   **dest:** 这是一个指向目标数组的指针，它应该包含一个 C 字符串，并且应该足够大以包含连接的结果字符串。
*   **src:** 这是要追加的字符串。这不应与目的地重叠。

**返回值:**strcat()函数返回 dest，即指向目标字符串的指针。

**应用:**给定 C++ 中的两个字符串 src 和 dest，我们需要在 dest 指向的字符串末尾追加 src 指向的字符串。

**示例:**

```cpp
Input: src = "ForGeeks"
       dest = "Geeks"
Output: "GeeksForGeeks"

Input: src = "World"
       dest = "Hello "
Output: "Hello World"
```

下面是实现上述方法的 C 程序:

## C

```cpp
// C program to implement
// the above approach
#include <stdio.h>
#include <string.h>

// Driver code
int main(int argc,
         const char* argv[])
{
    // Define a temporary variable
    char example[100];

    // Copy the first string into
    // the variable
    strcpy(example, "Geeks");

    // Concatenate this string
    // to the end of the first one
    strcat(example, "ForGeeks");

    // Display the concatenated strings
    printf("%s\n", example);

    return 0;
}
```

**Output:**

```cpp
GeeksForGeeks

```

**注意:**
目标弦要做得足够大，可以容纳最后一根弦。