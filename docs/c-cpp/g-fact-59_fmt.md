# C/C++ 运算符优先级

## 前缀与后缀自增/自减运算符的优先级

> 原文: [https://www.geeksforgeeks.org/g-fact-59/](https://www.geeksforgeeks.org/g-fact-59/)

在 C/C++ 中，前缀 `++`（或前缀 `--`）的优先级与解引用 `*` 运算符的优先级相同，而后缀 `++`（或后缀 `--`）的优先级高于前缀 `++` 和 `*` 两者。
如果 `p` 是指针，那么 `*p++` 相当于 `*(p++)`，而 `++*p` 相当于 `++(*p)`（前缀 `++` 和 `*` 都是右结合的）。
例如，程序 1 打印 `'h'`，程序 2 打印 `'e'`。

### 示例 1

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

`输出:`

```cpp
  h
```

### 示例 2

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

`输出:`

```cpp
  e
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。