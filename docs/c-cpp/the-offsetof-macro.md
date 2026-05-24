# OFFSETOF()宏

> 原文:[https://www.geeksforgeeks.org/the-offsetof-macro/](https://www.geeksforgeeks.org/the-offsetof-macro/)

我们知道结构中的元素将按照它们声明的顺序存储。

如何提取结构中元素的位移？我们可以利用宏的[偏移量。](http://en.wikipedia.org/wiki/Offsetof)

通常我们把结构和联合类型(或者带有琐碎构造函数的*类*)称为*普通旧数据* (POD)类型，这些类型将用于*聚合其他数据类型*。以下非标准宏可用于从结构变量的基址获取元素的字节位移。

```cpp
#define OFFSETOF(TYPE, ELEMENT) ((size_t)&(((TYPE *)0)->ELEMENT))
```

零被转换为结构类型，所需元素的地址被访问，该地址被转换为 *size_t* 。根据标准*尺寸 _t* 是类型*无符号整数*。整个表达式的结果是在结构中放置元素后的字节数。

例如，以下代码返回 16 个字节(32 位机器上考虑填充)作为结构 Pod 中字符变量 *c* 的位移。

```cpp
#include <stdio.h>

#define OFFSETOF(TYPE, ELEMENT) ((size_t)&(((TYPE *)0)->ELEMENT))

typedef struct PodTag
{
   int     i;
   double  d;
   char    c;
} PodType;

int main()
{
   printf("%d", OFFSETOF(PodType, c) );

   getchar();
   return 0;
}
```

在上面的代码中，下面的表达式将返回元素 *c* 在结构 *PodType* 中的位移。

```cpp
OFFSETOF(PodType, c);
```

预处理阶段后，上述宏扩展到

```cpp
((size_t)&(((PodType *)0)->c))
```

由于我们将 0 视为结构变量的地址，c 将放在其基址的 16 个字节之后，即 0x00 + 0x10。在结构元素上应用&返回元素地址 0x10。将地址转换为*无符号整数* (size_t)会导致元素在结构中的字节数。

**注:**我们可以认为地址运算符&是多余的。如果宏中没有地址运算符，代码将取消引用位于空地址的结构元素。它会在运行时导致访问冲突异常(分段错误)。

*注意，根据编译器行为，还有其他方法可以实现宏的 offsetof。最终目标是提取元素的位移。* ***我们将在另一篇文章中看到在喜欢的列表中使用 offsetof 宏来连接相似的对象(例如线程池)。***

文由**文基**整理。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。

参考文献:

1. [Linux 内核代码](http://www.kernel.org/)。

2.[http://msdn.microsoft.com/en-us/library/dz4y9b9a.aspx](http://msdn.microsoft.com/en-us/library/dz4y9b9a.aspx)

3. [GNU C/C++ 编译器文档](http://gcc.gnu.org/onlinedocs/)