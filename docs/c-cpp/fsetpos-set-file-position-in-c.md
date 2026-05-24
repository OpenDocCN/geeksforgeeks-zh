# C

中的偏移量()(设置文件位置)

> 原文:[https://www . geesforgeks . org/fset pos-set-file-position-in-c/](https://www.geeksforgeeks.org/fsetpos-set-file-position-in-c/)

**fsetpos()** 功能将文件位置指示器移动到位置所指向的对象所指定的位置。当执行 **fsetpos()** 时，文件结束指示器复位。
**申报**

**参数–**

*   **流–**这是一个指向文件对象的指针，用于标识流。
*   **位置–**这是指向 fpos_t 对象的指针，该对象包含以前用 fgetpos 获得的位置。

**返回–**如果成功，返回**零**否则返回非零值。

## C

```cpp
// c code to demonstrate fsetpos() function.
#include <stdio.h>
int main () {
   FILE *fp;
   fpos_t position;

   /*write your own file name.
    My file name is "myfile.txt"*/
   fp = fopen("myfile.txt","w+");
   fgetpos(fp, &position);
   fputs("HelloWorld!", fp);

   fsetpos(fp, &position);

   // previous function is override
   fputs("geeksforgeeks", fp);
   fclose(fp);

   return(0);
}
```

**输出–**

```cpp
geeksforgeeks
```

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。