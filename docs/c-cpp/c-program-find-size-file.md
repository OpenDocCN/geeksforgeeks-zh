# C 程序查找文件大小

> 原文:[https://www.geeksforgeeks.org/c-program-find-size-file/](https://www.geeksforgeeks.org/c-program-find-size-file/)

给定一个文本文件，找到它的字节大小。

示例:

```cpp
Input :  file_name = "a.txt"
         Let "a.txt" contains "geeks"
Output : 6 Bytes
There are 5 bytes for 5 characters then an extra
byte for end of file.

Input :  file_name = "a.txt"
         Let "a.txt" contains "geeks for geeks"
Output : 16 Bytes

```

这个想法是在 C 使用 [fseek()，在 C](https://www.geeksforgeeks.org/fseek-in-c-with-example/) 使用 [ftell。使用 fseek()，我们将文件指针移动到末尾，然后使用 ftell()，我们找到它的位置，实际上是以字节为单位的大小。](https://www.geeksforgeeks.org/ftell-c-example/)

 [```cpp
// C program to find the size of file
#include <stdio.h>

long int findSize(char file_name[])
{
    // opening the file in read mode
    FILE* fp = fopen(file_name, "r");

    // checking if the file exist or not
    if (fp == NULL) {
        printf("File Not Found!\n");
        return -1;
    }

    fseek(fp, 0L, SEEK_END);

    // calculating the size of the file
    long int res = ftell(fp);

    // closing the file
    fclose(fp);

    return res;
}

// Driver code
int main()
{
    char file_name[] = { "a.txt" };
    long int res = findSize(file_name);
    if (res != -1)
        printf("Size of the file is %ld bytes \n", res);
    return 0;
}
```](https://www.geeksforgeeks.org/ftell-c-example/)