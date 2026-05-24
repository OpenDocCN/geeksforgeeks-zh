# C/c++ 中常用的字符串函数并举例

> 原文:[https://www . geesforgeks . org/常用字符串-函数-in-c-c-with-examples/](https://www.geeksforgeeks.org/commonly-used-string-functions-in-c-c-with-examples/)

[**C 中的字符串**](https://www.geeksforgeeks.org/strings-in-c-2/) :字符串定义为一个字符数组。字符数组和字符串的区别在于字符串以特殊字符“\0”结尾。
**一些最常用的字符串函数有:**

*   [**strcat**](https://www.geeksforgeeks.org/strcat-vs-strncat-c/):strcat()函数会在目标字符串的末尾追加一个源字符串的副本。strcat()函数接受两个参数:
    1) dest
    2) src
    它将在目标字符串中追加源字符串的副本。**dest 末尾的终止字符被 src 的第一个字符替换。**
    **返回值:**strcat()函数返回 dest，即指向目的字符串的指针。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// strcat
#include <cstring>
#include <iostream>
using namespace std;
int main()
{
    char dest[50] = "This is an";
    char src[50] = " example";

    strcat(dest, src);
    cout << dest;
    return 0;
}
```

**Output:** 

```cpp
This is an example
```

*   [**strchr**](https://www.geeksforgeeks.org/strrchr-function-in-cpp/):在 C/C++ 中，strchr()是一个预定义的用于字符串处理的函数。cstring 是字符串函数所需的头文件。
    这个函数返回一个指向字符串中最后一个字符的指针。
    我们要查找的最后一次出现的字符作为第二个参数传递给函数，我们要查找的字符串作为第一个参数传递给函数。
    **语法**

```cpp
char *strrchr(const char *str, int c) 
```

*   这里，str 是字符串，c 是要定位的字符。它作为其 int 提升传递，但在内部转换回 char。
    **例:**

## C++

```cpp
// C++ code to demonstrate the working of
// strrchr()
#include <cstring>
#include <iostream>
using namespace std;

// Driver function
int main()
{

    // initializing variables
    char st[] = "GeeksforGeeks";
    char ch = 'e';
    char* val;

    // Use of strrchr()
    // returns "ks"
    val = strrchr(st, ch);

    cout <<"String after last " << ch << " is :  " << val << endl;

    char ch2 = 'm';

    // Use of strrchr()
    // returns null
    // test for null
    val = strrchr(st, ch2);

    cout <<"String after last " << ch2 << " is :  " << val << endl;

    return (0);
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C code to demonstrate the working of
// strrchr()

#include <stdio.h>
#include <string.h>

// Driver function
int main()
{

    // initializing variables
    char st[] = "GeeksforGeeks";
    char ch = 'e';
    char* val;

    // Use of strrchr()
    // returns "ks"
    val = strrchr(st, ch);

    printf("String after last %c is :  %s \n",
           ch, val);

    char ch2 = 'm';

    // Use of strrchr()
    // returns null
    // test for null
    val = strrchr(st, ch2);

    printf("String after last %c is :  %s ",
           ch2, val);

    return (0);
}
```

**Output:** 

```cpp
String after last e is :  eks 
String after last m is :  (null)
```

*   [**strcmp**](https://www.geeksforgeeks.org/strcmp-in-c-cpp/) : strcmp()是内置库函数，在 **< string.h >** 头文件中声明。该函数将两个字符串作为参数，并按字典顺序比较这两个字符串。
    **语法:**:

```cpp
int strcmp(const char *leftStr, const char *rightStr );
```

*   在上面的原型中，函数 srtcmp 将两个字符串作为参数，并基于字符串的比较返回一个整数值。
    *   strcmp()按字典顺序比较**两个字符串**表示它从第一个字符开始逐字符比较，直到两个字符串中的字符相等或遇到空字符。
    *   如果两个字符串中的第一个字符相等，那么这个函数将检查第二个字符，如果这个字符也相等，那么它将检查第三个字符，以此类推
    *   这一过程将继续，直到任一字符串中的字符为空或字符不相等。
*   [**strcpy**](https://www.geeksforgeeks.org/strcpy-in-c-cpp/) : strcpy()是 C/C++ 中的标准库函数，用于将一个字符串复制到另一个字符串。在 C 语言中，它存在于 **string.h** 头文件中，在 C++ 中，它存在于 **cstring** 头文件中。
    **语法:**

```cpp
char* strcpy(char* dest, const char* src);
```

*   **参数:**该方法接受以下参数:
    *   **目的地**:指向要复制内容的目标数组的指针。

    *   **src:** 将要复制的字符串。

*   [**strlen**](https://www.geeksforgeeks.org/strlen-function-in-c/):**strlen()**函数计算给定字符串的长度。 **strlen()** 函数在 **string.h** 头文件中定义。它不计算空字符' \0 '。
    **语法:**

```cpp
int strlen(const char *str);
```

*   **参数:**
    *   **str:** 它代表我们必须找到其长度的字符串变量。
*   [**strncat**](https://www.geeksforgeeks.org/strncat-function-in-c-cpp/) :在 C/C++ 中，strncat()是一个预定义的用于字符串处理的函数。 **string.h** 是字符串函数需要的头文件。
    该函数将 src 指向的字符串中不超过 **n 个**字符追加到 dest 指向的字符串末尾，并加上一个终止的空字符。字符串的初始字符(src)会覆盖字符串(dest)末尾的空字符。因此，字符串(dest)的长度变为 strlen(dest)+n。但是，如果字符串(src)的长度小于 **n** ，则仅复制直到终止空字符的内容，并且字符串(dest)的长度变为 strlen(src) + strlen(dest)。
    在以下情况下，行为未定义
    *   琴弦重叠了。
    *   dest 数组不够大，无法追加 src 的内容。
    *   **dest** :我们要追加的字符串。
    *   **src** :要追加“n”个字符的字符串。
    *   **n** :表示要追加的最大字符数。size_t 是无符号整数类型。
*   [**strncmp**](https://www.geeksforgeeks.org/stdstrncmp-in-c/):**STD::strncmp()**函数按字典顺序比较两个空终止字符串中不超过计数的字符，并根据结果返回一个整数。
    *   该函数以两个字符串和一个数字 **num** 作为参数，最多先比较两个字符串的 **num** 字节。
    *   **num** 应该最多等于最长字符串的长度。如果定义的**数**大于字符串长度，则进行比较，直到任一字符串的空字符(' 0 ')为止。
    *   该函数按字典顺序比较两个字符串。它从每个字符串的第一个字符开始比较。如果它们彼此相等，它会继续并比较每个字符串的下一个字符，以此类推。
    *   该比较过程停止，直到达到任一字符串的终止空字符或两个字符串的**号**字符匹配。
*   [**strncpy**](https://www.geeksforgeeks.org/why-strcpy-and-strncpy-are-not-safe-to-use/):strncpy()函数与 strcpy()函数类似，只是最多复制 n 个字节的 src。如果 src 的前 n 个字符中没有空字符，则放置在 dest 中的字符串不会以空结尾。如果 src 的长度小于 n，strncpy()会向 dest 写入额外的空字符，以确保总共写入 n 个字符。
    **语法:**

```cpp
char *strncpy( char *dest, const char *src, size_t n )
```

*   **参数:**该函数接受两个参数，如上所述，如下所述:
    *   **src:** 将要复制的字符串。
    *   **dest:** 指向要复制内容的目标数组的指针。
    *   **n:** 从 src 复制到 dest 的前 n 个字符。
*   [**str chr**](https://www.geeksforgeeks.org/strrchr-function-in-c-c/):C/c++ 中的**str chr()**函数定位字符串中最后一个出现的字符。它返回一个指向字符串中最后一个匹配项的指针。终止的空字符被认为是 C 字符串的一部分。因此，也可以定位它来检索指向字符串末尾的指针。在 **cstring** 头文件中定义。
    **语法:**

```cpp
const char* strrchr( const char* str, int ch )
            or
char* strrchr( char* str, int ch )
```

*   **参数:**该函数采用两个强制参数，描述如下:
    *   **字符串:**指定要搜索的空终止字符串的指针。
    *   **ch:** 指定要搜索的字符。