# “char a”和“char a[1]”有什么区别？

> 原文:[https://www.geeksforgeeks.org/difference-char-char-a1/](https://www.geeksforgeeks.org/difference-char-char-a1/)

问题来源:[阿里科面试](https://www.geeksforgeeks.org/aricent-interview-set-1-campus/)

虽然这两个表达式都可以用来创建一个变量来存储一个字符，但有以下区别。

1)“char a”表示字符变量，“char a[1]”表示大小为 1 的字符数组。

2)如果我们打印字符 a 的值，我们得到字符的 ASCII 值(如果使用%d)。如果我们打印 char a[1]的值，我们得到数组中唯一元素的地址。

```cpp
#include <stdio.h>

int main ()
{
  char a1 = 'A';
  char a2[1] = {'A'};
  printf("%d  %d", a1, a2);
  return 0;
}
```

输出:

```cpp
65
An address

```

本文由 **Abhishek** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。