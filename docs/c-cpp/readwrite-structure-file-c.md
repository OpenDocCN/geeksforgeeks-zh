# 对 C 语言文件的读/写结构

> 原文:[https://www.geeksforgeeks.org/readwrite-structure-file-c/](https://www.geeksforgeeks.org/readwrite-structure-file-c/)

先决条件:[C 中的结构](https://www.geeksforgeeks.org/structures-c/)
对于文件写入，使用 **fprintf** 和 **putc** 很容易将字符串或 int 写入文件，但是在写入结构内容时可能会遇到困难。 **fwrite** 和 **fread** 在您想要写入和读取数据块时使任务变得更加容易。

*   **fwrite :** 以下是 fwrite 功能的声明

```cpp
size_t fwrite(const void *ptr, size_t size, size_t nmemb, FILE *stream)
ptr - This is pointer to array of elements to be written
size -  This is the size in bytes of each element to be written
nmemb - This is the number of elements, each one with a size of size bytes
stream - This is the pointer to a FILE object that specifies an output stream
```

## C

```cpp
// C program for writing
// struct to file
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// a struct to read and write
struct person
{
    int id;
    char fname[20];
    char lname[20];
};

int main ()
{
    FILE *outfile;

    // open file for writing
    outfile = fopen ("person.dat", "w");
    if (outfile == NULL)
    {
        fprintf(stderr, "\nError opened file\n");
        exit (1);
    }

    struct person input1 = {1, "rohan", "sharma"};
    struct person input2 = {2, "mahendra", "dhoni"};

    // write struct to file
    fwrite (&input1, sizeof(struct person), 1, outfile);
    fwrite (&input2, sizeof(struct person), 1, outfile);

    if(fwrite != 0)
        printf("contents to file written successfully !\n");
    else
        printf("error writing file !\n");

    // close file
    fclose (outfile);

    return 0;
}
```

**输出:**

```cpp
gcc demowrite.c
./a.out
contents to file written successfully!
```

*   **fread :** 下面是 fread 函数的声明

```cpp
size_t fread(void *ptr, size_t size, size_t nmemb, FILE *stream)
ptr - This is the pointer to a block of memory with a minimum size of size*nmemb bytes.
size - This is the size in bytes of each element to be read.
nmemb - This is the number of elements, each one with a size of size bytes.
stream - This is the pointer to a FILE object that specifies an input stream.
```

## C

```cpp
// C program for reading
// struct from a file
#include <stdio.h>
#include <stdlib.h>

// struct person with 3 fields
struct person
{
    int id;
    char fname[20];
    char lname[20];
};

// Driver program
int main ()
{
    FILE *infile;
    struct person input;

    // Open person.dat for reading
    infile = fopen ("person.dat", "r");
    if (infile == NULL)
    {
        fprintf(stderr, "\nError opening file\n");
        exit (1);
    }

    // read file contents till end of file
    while(fread(&input, sizeof(struct person), 1, infile))
        printf ("id = %d name = %s %s\n", input.id,
        input.fname, input.lname);

    // close file
    fclose (infile);

    return 0;
}
```

**输出:**

```cpp
gcc demoread.c
./a.out
id = 1   name = rohan sharma
id = 2   name = mahendra dhoni
```

本文由**曼德普·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。