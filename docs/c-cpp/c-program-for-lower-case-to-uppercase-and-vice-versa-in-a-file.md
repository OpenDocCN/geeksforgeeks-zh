# 在文件

中，将小写字母编程为大写字母，反之亦然

> 原文:[https://www . geesforgeks . org/c-program-for-小写到大写-反之亦然-in-a-file/](https://www.geeksforgeeks.org/c-program-for-lower-case-to-uppercase-and-vice-versa-in-a-file/)

**小写到大写**

给定一个文本文件(gfg.txt)，我们的任务是将文件的所有小写字符转换成大写。

示例:

```cpp
Input: (content inside file (gfg.txt)
Geeks Classes:
An extensive classroom programme
by GeeksforGeeks to build and enhance
Data Structures and Algorithm concepts

Output: (content inside file (gfg.txt)
GEEKS CLASSES:
AN EXTENSIVE CLASSROOM PROGRAMME
BY GEEKSFORGEEKS TO BUILD AND ENHANCE
DATA STRUCTURES AND ALGORITHM CONCEPTS

```

方法:
在**打开文件 gfg.txt，读取**模式。检查打开或定位文件时是否有任何错误。如果是，则抛出一条错误消息。

如果找到了文件，那么在 while 循环的帮助下，使用[将该文件的所有字符转换成大写。
通过传递文件指针，使用 **fclose()** 函数关闭文件。](https://www.geeksforgeeks.org/conversion-whole-string-uppercase-lowercase-using-stl-c/)

```cpp
// C++ program to convert
// all lower case characters of a file
// into Upper Case
#include <bits/stdc++.h>

int main()
{
    // initializing the file pointer
    FILE* fptr;

    // name of the file as sample.txt
    char file[50] = { "gfg.txt" };
    char ch;

    // opening the file in read mode
    fptr = fopen(file, "r");
    ch = fgetc(fptr);

    // converting into upper case
    while (ch != EOF) {

        // converting char to upper case
        ch = toupper(ch);
        printf("%c", ch);
        ch = fgetc(fptr);
    }

    // closing the file
    fclose(fptr);

    return 0;
}
```

输出:

```cpp
GEEKS CLASSES:
AN EXTENSIVE CLASSROOM PROGRAMME
BY GEEKSFORGEEKS TO BUILD AND ENHANCE
DATA STRUCTURES AND ALGORITHM CONCEPTS

```

**大写到小写:**
与上面类似，只是使用 **[来降低](https://www.geeksforgeeks.org/isupper-islower-application-c/)** 功能来代替**去覆盖**
示例:

```cpp
Input: (content inside file (gfg.txt)
Geeks Classes:
AN EXTENSIVE CLASSROOM PROGRAMME
BY GEEKSFORGEEKS TO BUILD AND ENHANCE
DATA STRUCTURES AND ALGORITHM CONCEPTS

Output: (content inside file (gfg.txt)
geeks classes:
an extensive classroom programme
by geeksforgeeks to build and enhance
data structures and algorithm concepts

```

```cpp
// C++ program to convert all upper
// case characters of a file
// into lower Case
#include <bits/stdc++.h>

int main()
{

    // initializing the file pointer
    FILE* fptr;

    // name of the file as gfg.txt
    char file[30] = { "gfg.txt" };
    char ch;

    // opening the file in read mode
    fptr = fopen(file, "r");
    ch = fgetc(fptr);

    // converting into lower case
    while (ch != EOF) {

        // converting char to lower case
        ch = tolower(ch);
        printf("%c", ch);
        ch = fgetc(fptr);
    }

    // closing the file
    fclose(fptr);

    return 0;
}
```

**输出:**

```cpp
geeks classes:
an extensive classroom programme
by geeksforgeeks to build and enhance
data structures and algorithm concepts
```

注意:

> 1.使文件 gfg.txt 脱机运行这个程序，并在其中存储一些字符。
> 2。请确保您制作的文件与代码中使用的文件同名，并且位于存储程序的同一文件夹中。