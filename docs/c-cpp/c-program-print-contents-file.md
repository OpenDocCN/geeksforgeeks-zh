# C 程序打印文件内容

> 原文:[https://www . geesforgeks . org/c-program-print-contents-file/](https://www.geeksforgeeks.org/c-program-print-contents-file/)

[fopen()](http://www.cplusplus.com/reference/cstdio/fopen/) 用于打开， [fclose()](http://www.cplusplus.com/reference/cstdio/fclose/) 用于关闭 C

```cpp
#include <stdio.h>
#include <stdlib.h> // For exit()

int main()
{
    FILE *fptr;

    char filename[100], c;

    printf("Enter the filename to open \n");
    scanf("%s", filename);

    // Open file
    fptr = fopen(filename, "r");
    if (fptr == NULL)
    {
        printf("Cannot open file \n");
        exit(0);
    }

    // Read contents from file
    c = fgetc(fptr);
    while (c != EOF)
    {
        printf ("%c", c);
        c = fgetc(fptr);
    }

    fclose(fptr);
    return 0;
}
```

中的文件

输出:

```cpp
Enter the filename to open
a.txt
/*Contents of a.txt*/
```