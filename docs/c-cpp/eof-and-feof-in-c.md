# C

中的 EOF、getc()和 feof()

> 原文:[https://www.geeksforgeeks.org/eof-and-feof-in-c/](https://www.geeksforgeeks.org/eof-and-feof-in-c/)

在 C/C++ 中，当到达文件末尾时， [getc()](http://www.cplusplus.com/reference/clibrary/cstdio/getc/) 返回 EOF。getc()在失败时也会返回 EOF。因此，仅比较 getc()返回的值和 EOF 不足以检查文件的实际结尾。为了解决这个问题，C 提供了 [feof()](http://en.wikipedia.org/wiki/Feof) ，只有当文件到达末尾时才返回非零值，否则返回 0。
例如，考虑以下 C 程序在屏幕上打印文件 *test.txt* 的内容。在程序中，首先将 getc()的返回值与 e of 进行比较，然后使用 feof()进行另一次检查。通过进行该检查，我们确保程序仅在到达文件结尾时打印*“到达文件结尾”*。如果 getc()由于任何其他原因返回 EOF，那么程序会打印*“出了问题”*

```cpp
#include <stdio.h>

int main()
{
  FILE *fp = fopen("test.txt", "r");
  int ch = getc(fp);
  while (ch != EOF) 
  {
    /* display contents of file on screen */ 
    putchar(ch); 

    ch = getc(fp);
  }

  if (feof(fp))
     printf("\n End of file reached.");
  else 
     printf("\n Something went wrong.");
  fclose(fp);

  getchar();
  return 0;
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。