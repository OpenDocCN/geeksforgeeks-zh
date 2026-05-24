# C

中 scanf()和 get()的区别

> 原文:[https://www . geesforgeks . org/scanf-and-get-in-c 之间的差异/](https://www.geeksforgeeks.org/difference-between-scanf-and-gets-in-c/)

### [【scanf()](https://www.geeksforgeeks.org/scanf-and-fscanf-in-c-simple-yet-poweful/)

*   它用于从标准输入(键盘)中读取输入(字符、字符串、数字数据)。
*   它用于读取输入，直到遇到空白、换行符或文件结尾(EOF)。

例如，请参见以下代码:

```cpp
// C program to see how scanf()
// stops reading input after whitespaces

#include <stdio.h>
int main()
{
    char str[20];
    printf("enter something\n");
    scanf("%s", str);
    printf("you entered: %s\n", str);

    return 0;
}
```

**这里输入由用户提供，输出如下:**

```cpp
Input: Geeks for Geeks
Output: Geeks

Input: Computer science
Output: Computer

```

### [获得](https://www.geeksforgeeks.org/fgets-gets-c-language/)

*   它用于从标准输入(键盘)读取输入。
*   它用于读取输入，直到遇到换行符或文件结束符。

```cpp
// C program to show how gets() 
// takes whitespace as a string.

#include <stdio.h>
int main()
{
    char str[20];
    printf("enter something\n");
    gets(str);
    printf("you entered : %s\n", str);
    return 0;
}
```

**这里输入将由用户提供如下**

```cpp
Input: Geeks for Geeks
Output: Geeks for Geeks

Input: Computer science
Output: Computer science

```

他们之间的主要**区别**是:

1.  **scanf()** 读取输入，直到遇到空白、换行符或文件结尾(EOF)，而**get()**读取输入，直到遇到换行符或文件结尾(EOF)，get()在遇到空白时不会停止读取输入，而是将空白作为字符串。
2.  **scanf** 可以读取不同数据类型的多个值，而**get()**只会获取字符串数据。

**差异可以用表格形式表示如下:**

| scanf() | 获取() |
| --- | --- |
| 当 scanf()用于读取字符串输入时，它会在遇到空白、换行符或文件结尾时停止读取 | 当 get()用于读取输入时，它会在遇到换行符或文件结尾时停止读取输入。
它不会在遇到空白时停止读取输入，因为它将空白视为字符串。 |
| 它用于读取任何数据类型的输入 | 它仅用于字符串输入。 |

### 如何使用 scanf()从用户处读取完整句子

实际上，我们可以使用 scanf()读取整个字符串。例如，我们可以在 scanf()中使用 **%[^\n]s** 来读取整个字符串。

```cpp
// C program to show how to read
// entire string using scanf()

#include <stdio.h>

int main()
{

    char str[20];
    printf("Enter something\n");

    // Here \n indicates that take the input
    // until newline is encountered
    scanf("%[^\n]s", str); 
    printf("%s", str);
    return 0;
}
```

上面的代码读取字符串，直到遇到换行符。

**示例:**

```cpp
Input: Geeks for Geeks
Output: Geeks for Geeks

Input: Computer science
Output: Computer science

```