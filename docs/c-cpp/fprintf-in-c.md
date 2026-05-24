# C

中的 fprintf()

> 原文:[https://www.geeksforgeeks.org/fprintf-in-c/](https://www.geeksforgeeks.org/fprintf-in-c/)

fprintf 用于打印文件中的内容，而不是 stdout 控制台。

```cpp
int fprintf(FILE *fptr, const char *str, ...);

```

例:

T3】CT5

```cpp
// C Program for the above approach  
#include<stdio.h>
int main()
{
    int i, n=2;
    char str[50];

    //open file sample.txt in write mode
    FILE *fptr = fopen("sample.txt", "w");
    if (fptr == NULL)
    {
        printf("Could not open file");
        return 0;
    }

    for (i = 0; i < n; i++)
    {
        puts("Enter a name");
        scanf("%[^\n]%*c", str);
        fprintf(fptr,"%d.%s\n", i, str);
    }
    fclose(fptr);

    return 0;
}
```

T6T1】

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。