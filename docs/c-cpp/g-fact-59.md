# C/c++

中后缀++ 和前缀++ 的优先级

> 原文:[https://www.geeksforgeeks.org/g-fact-59/](https://www.geeksforgeeks.org/g-fact-59/)

在 C/C++ 中，Prefix ++(或 Prefix–)的优先级与取消引用(*)运算符的优先级相同，Postfix ++(或 Postfix–)的优先级高于 Prefix ++ 和*两者。
如果 p 是指针，那么*p++ 相当于*(p++)，而++*p 相当于++( * p)(Prefix ++ 和*都是右关联的)。
例如，程序 1 打印*‘h’*，程序 2 打印*‘e’*。

## C

```cpp
// Program 1
#include<stdio.h>
int main()
{
  char arr[] = "geeksforgeeks";
  char *p = arr;
  ++*p;
  printf(" %c", *p);
  getchar();
  return 0;
}
```

**输出:**

```cpp
  h
```

## C

```cpp
// Program 2
#include<stdio.h>
int main()
{
  char arr[] = "geeksforgeeks";
  char *p = arr;
  *p++ ;
  printf(" %c", *p);
  getchar();
  return 0;
}
```

**输出:**

```cpp
  e
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。