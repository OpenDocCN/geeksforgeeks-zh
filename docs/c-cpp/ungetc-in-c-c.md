# C/c++

中的 ungetc()

> 原文:[https://www.geeksforgeeks.org/ungetc-in-c-c/](https://www.geeksforgeeks.org/ungetc-in-c-c/)

**ungetc()** 函数获取一个字符，并将其推回到输入流中。它与 [getc()](https://www.geeksforgeeks.org/eof-and-feof-in-c/) 函数相反，后者从输入流中读取单个字符。此外，ungetc()是一个输入函数，而不是输出函数。
**语法:**

```cpp
int ungetc(int char, FILE *stream)
```

**参数:**

*   **char** :指定要放回的角色的 int 提升。放回时，该值在内部转换为无符号字符。
*   **流**:指定标识输入流的 FILE 对象的指针。

**返回值:**函数返回两种值。

*   成功后，ungetc()函数返回字符 ch。
*   失败时，不改变流就返回 EOF。

**功能要点:**

1.  ungetc()函数将 char 指定的字节(转换为无符号字符)推回到 stream 指向的输入流中。
2.  被推回的字节由该流上的后续读取以与其推回相反的顺序返回。
3.  对文件定位函数(fseek()、fsetpos()、或 rewind())的成功中间调用(流所指向的流)会丢弃流的任何回推字节。
4.  流对应的外部存储应保持不变。
5.  对 ungetc()的成功调用会清除流的文件结束指示符。
6.  读取或丢弃所有回推字节后，流的文件位置指示符的值应与回推字节之前的值相同。
7.  每次成功调用 ungetc()时，文件位置指示器都会递减，如果在调用前其值为 0，则在调用后其值未指定。

下面的程序说明了上述功能。

**程序 1:**

```cpp
#include <stdio.h>

int main()
{
    FILE* f;
    int char;
    char buffer[256];

    // read a file
    f = fopen("use1.txt", "r");

    // when no data
    if (f == NULL) {
        printf("Error in opening file");
        return (-1);
    }

    // read lines till end
    while (!feof(f)) {

        // get line
        char = getc(f);
        // replace ! with +
        if (char == '!') {
            ungetc('+', f);
        }
        // if not
        else {
            ungetc(c, f);
        }
        fgets(buffer, 255, f);
        fputs(buffer, stdout);
    }
    return 0;
}
```

让我们假设，我们有一个文本文件 use1.txt，它包含以下数据。该文件将用作我们示例程序的输入，然后输入和输出如下所示:

```cpp
Input: !c standard library
       !library function stdio.h-ungetc()
Output: +c standard library
        +library function stdio.h-ungetc()

```

**程序 2:**

```cpp
// C program for taking input till we
// get 1 at the input 
#include <stdio.h>
int main()
{
    int ch;

    // reads characters from the stdin and show
    // them on stdout until encounters '1'
    while ((ch = getchar()) != '1')
        putchar(ch);

    // ungetc() returns '1' previously
    // read back to stdin
    ungetc(ch, stdin);

    // getchar() attempts to read
    // next character from stdin
    // and reads character '1' returned
    // back to the stdin by ungetc()
    ch = getchar();

    // putchar() displays character
    putchar(ch);
    return 0;
}
```