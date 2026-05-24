# 对 C 中结构变量的操作

> 原文:[https://www.geeksforgeeks.org/g-fact-68/](https://www.geeksforgeeks.org/g-fact-68/)

在 C 语言中，唯一可以应用于*结构*变量的操作是赋值。在*结构*变量上不允许任何其他操作(例如相等检查)。
例如，程序 1 运行没有任何错误，程序 2 编译失败。

**程序 1**

```cpp
#include <stdio.h>

struct Point {
  int x;
  int y;
};

int main()
{
  struct Point p1 = {10, 20};
  struct Point p2 = p1; // works: contents of p1 are copied to p2
  printf(" p2.x = %d, p2.y = %d", p2.x, p2.y);
  getchar();
  return 0;
}
```

**节目 2**

```cpp
#include <stdio.h>

struct Point {
  int x;
  int y;
};

int main()
{
  struct Point p1 = {10, 20};
  struct Point p2 = p1; // works: contents of p1 are copied to p2
  if (p1 == p2)  // compiler error: cannot do equality check for         
                  // whole structures
  {
    printf("p1 and p2 are same ");
  }
  getchar();
  return 0;
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。