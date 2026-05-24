# C 中的数据类型

> 原文:[https://www.geeksforgeeks.org/data-types-in-c/](https://www.geeksforgeeks.org/data-types-in-c/)

C 语言中的每个变量都有一个关联的数据类型。每种数据类型需要不同的内存量，并且有一些特定的操作可以在其上执行。让我们逐一简单描述一下:
下面是 C 语言中使用的一些非常常见的数据类型的例子:

*   **char:**c 语言中最基本的数据类型，它存储单个字符，几乎所有编译器都需要单字节内存。
*   **int:** 顾名思义，int 变量用于存储整数。
*   **浮点数:**用于存储单精度的十进制数(带浮点值的数)。
*   **double:** 用于存储双精度的十进制数(带浮点值的数)。

不同的数据类型也有不同的存储数字的范围。这些范围可能因编译器而异。下面列出了 32 位 gcc 编译器的内存需求和格式说明符。

<figure class="table">T35】无符号短 int
T38】2【T39

长双

| Data type
 | Memory (bytes)
 | Range
 | Format specifier
 |
| --- | --- | --- | --- |
| 短 int
 | 2
 | -32,768 to 32,767
 | % HD
 |
| 4
 | -2,147,483,648 to 2,147,483,647
 | % d
 |
| 长 int
 | 4
 | -2，147，483 to(2^63)-1
 | % lld
 |
| Unsigned long integer
 | 8
 | 0 to 18,446,744,073,709,551,615
 | %闪光
 |  | % f
 |
| Double
 | 8
 |  | % Lf
 |
| 16
 |

</figure>

我们可以使用 [sizeof()运算符](https://www.geeksforgeeks.org/sizeof-operator-c/)来检查变量的大小。各种数据类型的用法见下面的 C 程序:

## C

```cpp
#include <stdio.h>
int main()
{
    int a = 1;
    char b = 'G';
    double c = 3.14;
    printf("Hello World!\n");

    // printing the variables defined
    // above along with their sizes
    printf("Hello! I am a character. My value is %c and "
           "my size is %lu byte.\n",
           b, sizeof(char));
    // can use sizeof(b) above as well

    printf("Hello! I am an integer. My value is %d and "
           "my size is %lu  bytes.\n",
           a, sizeof(int));
    // can use sizeof(a) above as well

    printf("Hello! I am a double floating point variable."
           " My value is %lf and my size is %lu bytes.\n",
           c, sizeof(double));
    // can use sizeof(c) above as well

    printf("Bye! See you soon. :)\n");

    return 0;
}
```

**输出:**

```cpp
Hello World!
Hello! I am a character. My value is G and my size is 1 byte.
Hello! I am an integer. My value is 1 and my size is 4  bytes.
Hello! I am a double floating point variable. My value is 3.140000 and my size i
s 8 bytes.
Bye! See you soon. :)

```

[Quiz on Data Types in C](https://www.geeksforgeeks.org/c-language-2-gq/data-types-gq/)This article is contributed by Ayush Jaggi. Please write comments if you find anything incorrect, or you want to share more information about the topic discussed above