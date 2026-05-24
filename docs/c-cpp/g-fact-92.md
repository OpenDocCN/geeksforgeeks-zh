# 在 C 中初始化变量大小的数组

> 原文:[https://www.geeksforgeeks.org/g-fact-92/](https://www.geeksforgeeks.org/g-fact-92/)

C99 标准允许可变大小的阵列(参见[和](https://www.geeksforgeeks.org/g-fact-8/))。但是，与普通数组不同，可变大小的数组不能被初始化。

例如，以下程序在 C99 兼容的编译器上编译并运行良好。

```cpp
#include<stdio.h>

int main()
{
  int M = 2;
  int arr[M][M];
  int i, j;
  for (i = 0; i < M; i++)
  {
    for (j = 0; j < M; j++)
    {
       arr[i][j] = 0;
       printf ("%d ", arr[i][j]);
    }
    printf("\n");
  }
  return 0;
}
```

输出:

```cpp
0 0
0 0

```

但是以下操作失败，出现编译错误。

```cpp
#include<stdio.h>

int main()
{
  int M = 2;
  int arr[M][M] = {0}; // Trying to initialize all values as 0
  int i, j;
  for (i = 0; i < M; i++)
  {
    for (j = 0; j < M; j++)
       printf ("%d ", arr[i][j]);
    printf("\n");
  }
  return 0;
}
```

输出:

```cpp
Compiler Error: variable-sized object may not be initialized

```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。