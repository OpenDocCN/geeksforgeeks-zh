# C fopen()函数示例

> 原文:[https://www . geeksforgeeks . org/c-fopen-function-with-examples/](https://www.geeksforgeeks.org/c-fopen-function-with-examples/)

**先决条件:**[C 中文件处理基础](https://www.geeksforgeeks.org/basics-file-handling-c/)
C 中的 **fopen()方法**是一个库函数，用于打开文件以执行各种操作，包括读取、写入等。以及各种模式。如果该文件存在，则打开该特定文件，否则创建一个新文件。

**语法:**

```cpp
FILE *fopen(const char *file_name, const char *mode_of_operation);
```

**参数:**该方法接受字符类型的两个参数:

1.  **file_name:** 这是 C 字符串类型，接受需要打开的文件名。
2.  **mode_of_operation:** 这也是 C 字符串类型，指的是文件访问的模式。以下是 C 语言的文件访问模式:
    1.  **“r”–**搜索文件。 ***打开文件只读**。*如果文件打开成功，fopen()会将其加载到内存中，并设置一个指向其中第一个字符的指针。如果文件无法打开，fopen()返回空值。
    2.  **“w”–**搜索文件。如果文件已经存在，其内容将被覆盖。如果文件不存在，则会创建一个新文件。如果无法打开文件，则返回空值。 ***它创建一个只写(不读)的新文件。***
    3.  **“a”–**搜索文件。如果文件打开成功，fopen()会将其加载到内存中，并设置一个指向其中最后一个字符的指针。如果文件不存在，则会创建一个新文件。如果无法打开文件，则返回空值。 ***打开文件只是为了追加(写在文件末尾)。***
    4.  **“r+”–**搜索文件。 ***打开文件进行读写**。*如果打开成功，fopen()会将其加载到内存中，并设置一个指向其中第一个字符的指针。如果无法打开文件，则返回空值。
    5.  **“w+”–**搜索文件。如果文件存在，其内容将被覆盖。如果文件不存在，则会创建一个新文件。如果无法打开文件，则返回空值。***w 和 w+的区别在于，我们还可以读取使用 w+创建的文件。***
    6.  **“a+”–**搜索文件。如果文件打开成功，fopen()会将其加载到内存中，并设置一个指向其中最后一个字符的指针。如果文件不存在，则会创建一个新文件。如果无法打开文件，则返回空值。**打开文件进行读取和追加(写在文件末尾)。**

**返回值:**该函数用于在执行成功时返回文件指针，否则返回空值。

**例 1:**

## C

```cpp
// C program to illustrate fopen()

#include <stdio.h>
#include <stdlib.h>

int main()
{

    // pointer demo to FILE
    FILE* demo;

    // Creates a file "demo_file"
    // with file access as write-plus mode
    demo = fopen("demo_file.txt", "w+");

    // adds content to the file
    fprintf(demo, "%s %s %s", "Welcome",
            "to", "GeeksforGeeks");

    // closes the file pointed by demo
    fclose(demo);

    return 0;
}
```

运行以下命令时，将创建一个名为“demo_file”的新文件，其内容如下:

```cpp
Welcome to GeeksforGeeks
```

**示例 2:** 现在，如果我们希望查看文件，那么我们需要运行以下代码，该代码将打开文件并显示其内容。

## C

```cpp
// C program to illustrate fopen()

#include <stdio.h>

int main()
{

    // pointer demo to FILE
    FILE* demo;
    int display;

    // Creates a file "demo_file"
    // with file access as read mode
    demo = fopen("demo_file.txt", "r");

    // loop to extract every characters
    while (1) {
        // reading file
        display = fgetc(demo);

        // end of file indicator
        if (feof(demo))
            break;

        // displaying every characters
        printf("%c", display);
    }

    // closes the file pointed by demo
    fclose(demo);

    return 0;
}
```

**输出:**

```cpp
Welcome to GeeksforGeeks
```

**更多关于 C 语言文件处理的文章:**

1.  [C 语言文件处理基础](https://www.geeksforgeeks.org/basics-file-handling-c/)
2.  [写模式下现有文件的 fopen()](https://www.geeksforgeeks.org/fopen-for-an-existing-file-in-write-mode/)
3.  [C](https://www.geeksforgeeks.org/eof-and-feof-in-c/)中的 EOF、getc()和 feof()
4.  [文件打开模式(r 对 r+)](https://www.geeksforgeeks.org/file-opening-modesr-versus-r/)