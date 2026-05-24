# C 中的复合文字

> 原文:[https://www.geeksforgeeks.org/compound-literals-c/](https://www.geeksforgeeks.org/compound-literals-c/)

考虑下面 c 语言的程序。

```cpp
// Please make sure that you compile this program
// using a C compiler, not a C++ compiler (Save your
// file .cpp). If using online compiler, select "C"
#include <stdio.h>
int main()
{
   // Compound literal (an array is created without
   // any name and address of first element is assigned
   // to p.  This is equivalent to:
   // int arr[] = {2, 4, 6};
   // int *p = arr;
   int *p = (int []){2, 4, 6};

   printf("%d %d %d", p[0], p[1], p[2]);

   return 0;
}
```

输出:

```cpp
2 4 6
```

上面的例子是复合文字的例子。C 的 [C99 标准引入了复合文字。复合文字特性允许我们用给定的初始化值列表创建未命名的对象。在上面的示例中，创建了一个没有任何名称的数组。数组第一个元素的地址被分配给指针 p。](https://en.wikipedia.org/wiki/C99)

**有什么用？**
复合文字主要用于结构，在将结构变量传递给函数时特别有用。我们可以传递一个结构对象而不定义它
例如，考虑下面的代码。

```cpp
// Please make sure that you compile this program
// using a C compiler, not a C++ compiler (Save your
// file .cpp). If using online compiler, select "C"
#include <stdio.h>

// Structure to represent a 2D point
struct Point
{
   int x, y;
};

// Utility function to print point
void printPoint(struct Point p)
{
   printf("%d, %d", p.x, p.y);
}

int main()
{
   // Calling printPoint() without creating any temporary
   // Point variable in main()
   printPoint((struct Point){2, 3});

   /*  Without compound literal, above statement would have
       been written as
       struct Point temp = {2, 3};
       printPoint(temp);  */

   return 0;
}
```

输出:

```cpp
2, 3
```

本文由**希瓦姆·古普塔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。