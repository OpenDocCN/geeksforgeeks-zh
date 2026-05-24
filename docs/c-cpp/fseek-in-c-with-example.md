# C/c++ 中的 fseek()，示例

> 原文:[https://www.geeksforgeeks.org/fseek-in-c-with-example/](https://www.geeksforgeeks.org/fseek-in-c-with-example/)

fseek()用于将与给定文件相关联的文件指针移动到特定位置。
**语法:**

```cpp
int fseek(FILE *pointer, long int offset, int position)
pointer: pointer to a FILE object that identifies the stream.
offset: number of bytes to offset from position
position: position from where offset is added.

returns:
zero if successful, or else it returns a non-zero value 

```

位置定义文件指针需要相对移动的点。它有三个值:
SEEK_END:表示文件结束。
SEEK_SET:表示文件的开始。
SEEK_CUR:表示文件指针的当前位置。

```cpp
// C Program to demonstrate the use of fseek()
#include <stdio.h>

int main()
{
    FILE *fp;
    fp = fopen("test.txt", "r");

    // Moving pointer to end
    fseek(fp, 0, SEEK_END);

    // Printing position of pointer
    printf("%ld", ftell(fp));

    return 0;
}
```

输出:

```cpp
81

```

**解释**

文件 test.txt 包含以下文本:

```cpp
"Someone over there is calling you.
we are going for work.
take care of yourself."
```

当我们实现 fseek()时，我们将指针相对于文件结尾移动 0 距离，即指针现在指向文件结尾。因此输出为 81。

**相关文章:**T2【fseek vs 倒回 C

本文由 **Hardik Gaur** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。