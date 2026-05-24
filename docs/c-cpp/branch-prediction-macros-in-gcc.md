# GCC 中的分支预测宏

> 原文:[https://www . geesforgeks . org/branch-prediction-macros-in-gcc/](https://www.geeksforgeeks.org/branch-prediction-macros-in-gcc/)

Linux 内核中最常用的优化技术之一是“_ builtin _ expect”。当使用条件代码(if-else 语句)时，我们通常知道哪个分支是真的，哪个不是。如果编译器提前知道这些信息，就可以生成最优化的代码。

让我们看看“可能()”和“不太可能()”的宏定义“来自 linux 内核代码的宏”[http://lxr.linux.no/linux+v3.6.5/include/linux/compiler.h](http://lxr.linux.no/linux+v3.6.5/include/linux/compiler.h)【第 146 和 147 行】。

```cpp
#define likely(x)      __builtin_expect(!!(x), 1)
#define unlikely(x)    __builtin_expect(!!(x), 0)
```

在以下示例中，我们将分支标记为可能为真:

```cpp
const char *home_dir ;

home_dir = getenv("HOME");
if (likely(home_dir)) 
    printf("home directory: %s\n", home_dir);
else
    perror("getenv");
```

对于上面的例子，我们已经将“如果”条件标记为“可能()”true，所以编译器会将 true 代码放在分支之后，而将 false 代码放在分支指令内。这样编译器就可以实现优化。但不要盲目使用“可能()”和“不太可能()”宏。如果预测正确，则意味着跳转指令的周期为零，但如果预测错误，则需要几个周期，因为处理器需要刷新其流水线，这比没有预测更糟糕。

与其他 CPU 操作相比，访问内存是最慢的 CPU 操作。为了避免这种限制，中央处理器使用“中央处理器高速缓存”，例如 L1 高速缓存、L2 高速缓存等。缓存背后的想法是，将部分内存复制到 CPU 本身。我们可以比任何其他内存更快地访问高速缓存。但问题是，受限于“缓存内存”的大小，我们无法将整个内存复制到缓存中。因此，中央处理器必须猜测在不久的将来将使用哪个内存，并将该内存加载到中央处理器缓存中，上面的宏是将内存加载到中央处理器缓存中的提示。

本文由**纳伦德拉·康拉尔卡尔**整理。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。