# C 程序列出一个目录中的所有文件和子目录

> 原文:[https://www . geesforgeks . org/c-程序-列表-文件-子目录-目录/](https://www.geeksforgeeks.org/c-program-list-files-sub-directories-directory/)

```cpp
#include <stdio.h>
#include <dirent.h>

int main(void)
{
    struct dirent *de;  // Pointer for directory entry

    // opendir() returns a pointer of DIR type. 
    DIR *dr = opendir(".");

    if (dr == NULL)  // opendir returns NULL if couldn't open directory
    {
        printf("Could not open current directory" );
        return 0;
    }

    // Refer http://pubs.opengroup.org/onlinepubs/7990989775/xsh/readdir.html
    // for readdir()
    while ((de = readdir(dr)) != NULL)
            printf("%s\n", de->d_name);

    closedir(dr);    
    return 0;
}
```

输出:

```cpp
              All files and subdirectories 
              of current directory  
```