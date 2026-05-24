# 如何在 C 语言中不使用 free()的情况下解除内存分配？

> 原文:[https://www . geeksforgeeks . org/如何在不使用 c-in-free 的情况下解除内存分配/](https://www.geeksforgeeks.org/how-to-deallocate-memory-without-using-free-in-c/)

**问题:**如何在不使用“free()”函数的情况下动态解除分配分配内存。

**解决方案:**标准库函数 [realloc()](http://www.cplusplus.com/reference/clibrary/cstdlib/realloc/) 可以用来释放之前分配的内存。下面是来自“stdlib . h”

```cpp
void *realloc(void *ptr, size_t size);
```

的“realloc()”的函数声明

如果“size”为零，那么调用 realloc 就相当于“free(ptr)”。如果“ptr”为空，并且大小为非零，那么对 realloc 的调用就相当于“malloc(size)”。

让我们用一个简单的例子来验证一下。

```cpp
/* code with memory leak */
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
    int *ptr = (int*)malloc(10);

    return 0;
}
```

用 valgrind 工具检查泄漏总结。它显示了 10 字节的内存泄漏，以红色高亮显示。

```cpp
  [narendra@ubuntu]$ valgrind –leak-check=full ./free
  ==1238== LEAK SUMMARY:
  ==1238==    definitely lost: 10 bytes in 1 blocks.
  ==1238==      possibly lost: 0 bytes in 0 blocks.
  ==1238==    still reachable: 0 bytes in 0 blocks.
  ==1238==         suppressed: 0 bytes in 0 blocks.
[narendra@ubuntu]$

```

让我们修改上面的代码。

```cpp
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
    int *ptr = (int*) malloc(10);

    /* we are calling realloc with size = 0 */
    realloc(ptr, 0);

    return 0;
}
```

检查 valgrind 的输出。它显示内存泄漏是不可能的，用红色突出显示。

```cpp
  [narendra@ubuntu]$ valgrind –leak-check=full ./a.out
  ==1435== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 11 from 1)
  ==1435== malloc/free: in use at exit: 0 bytes in 0 blocks.
  ==1435== malloc/free: 1 allocs, 1 frees, 10 bytes allocated.
  ==1435== For counts of detected errors, rerun with: -v
  ==1435== All heap blocks were freed — no leaks are possible.
  [narendra@ubuntu]$

```

本文由“纳伦德拉·康拉尔卡尔”编辑，GeeksforGeeks 团队审核。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。