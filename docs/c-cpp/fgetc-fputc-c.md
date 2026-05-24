# C

中的 fgetc()和 fputc()

> 哎哎哎::1230【https://www . geeksforgeeks . org/fgetc-fputc-c/

**fgetc（）**

fgetc()用于一次从一个文件中获取单个字符的输入。该函数返回该函数读取的字符的 ASCII 码。它返回出现在文件指针指示位置的字符。读取字符后，文件指针前进到下一个字符。如果指针在文件的末尾或者发生错误，这个函数将返回一个文件。
**语法:**

```cpp
int fgetc(FILE *pointer)
pointer: pointer to a FILE object that identifies 
the stream on which the operation is to be performed.
```

## C

```cpp
// C program to illustrate fgetc() function
#include <stdio.h>

int main ()
{
    // open the file
    FILE *fp = fopen("test.txt","r");

    // Return if could not open file
    if (fp == NULL)
      return 0;

    do
    {
        // Taking input single character at a time
        char c = fgetc(fp);

        // Checking for end of file
        if (feof(fp))
            break ;

        printf("%c", c);
    }  while(1);

    fclose(fp);
    return(0);
}
```

输出:

```cpp
The entire content of file is printed character by
character till end of file. It reads newline character
as well.
```

**使用 fputc()**

fputc()用于一次向给定文件中写入一个字符。它在文件指针指示的位置写入给定字符，然后推进文件指针。
该函数返回写操作成功时写的字符，否则返回错误的电渗流。
**语法:**

```cpp
int fputc(int char, FILE *pointer)
char:  character to be written. 
This is passed as its int promotion.
pointer: pointer to a FILE object that identifies the 
stream where the character is to be written.
```

## C

```cpp
// C program to illustrate fputc() function
#include<stdio.h>
int main()
{
    int i = 0;
    FILE *fp = fopen("output.txt","w");

    // Return if could not open file
    if (fp == NULL)
      return 0;

    char string[] = "good bye", received_string[20];

    for (i = 0; string[i]!='\0'; i++)

        // Input string into the file
        // single character at a time
        fputc(string[i], fp);

    fclose(fp);
    fp = fopen("output.txt","r");

    // Reading the string from file
    fgets(received_string,20,fp);

    printf("%s", received_string);

    fclose(fp);
    return 0;
}
```

输出:

```cpp
good bye
```

当执行 fputc()时，字符串变量的字符被一个接一个地写入文件。当我们从文件中读取该行时，我们得到了与输入的字符串相同的字符串。
本文由**哈迪克·高尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。