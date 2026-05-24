# 为什么 C 被认为比其他语言更快？

> 原文:[https://www . geesforgeks . org/c-被认为更快的语言/](https://www.geeksforgeeks.org/c-considered-faster-languages/)

你可能会遇到这些说法，C 语言更优化，或者 C 语言的性能比高级语言更好，所以我将讨论这个假设的原因。

首先，让我们列出像 Java 这样的语言而不是 C 语言提供的功能:

1.  数组索引绑定检查
2.  未初始化的变量值检查
3.  检查内存泄漏
4.  检查空指针取消引用
5.  自动垃圾收集
6.  运行时类型检查
7.  异常处理

还有更多这样的功能在 C.
中没有出现额外的功能是有成本的，成本包括降低**速度**和增加**尺寸**。
举一个 C 和 Java 中动态分配的例子
**Java:**

```cpp
MyClass obj = new MyClass();
```

你考虑过 **obj** 的大小吗，答案是**没有**。原因是它是由语言本身在后台自动处理的，您不必为它编写特定的代码。
但是在 **C** 的情况下

```cpp
struct MyStruct *obj = malloc(sizeof(struct MyStruct));
```

正如您在上面的代码中看到的，分配指针引用的任务，大小的分配是由程序员明确完成的，最后释放分配的内存。
Thumb 执行环境(ThumbEE)支持数组绑定检查，它的其他特性包括对每个加载和存储指令的自动空指针检查，这是一个调用处理程序的特殊指令。
另一个原因是 C 与汇编语言的接近，在大多数情况下它的指令直接映射到汇编语言，C 离汇编语言只有一级或二级抽象，而 Java 离汇编语言至少有 3 级抽象。

**参考文献:**
1) [为什么-是-c-这么快-为什么-不是-其他语言-一样快或更快](https://stackoverflow.com/questions/418914/why-is-c-so-fast-and-why-arent-other-languages-as-fast-or-faster)T5】2)[ARM _ architecture # Thumb _ Execution _ Environment _ . 28 thumbee . 29](https://en.wikipedia.org/wiki/ARM_architecture#Thumb_Execution_Environment_.28ThumbEE.29)
3)[Linus Torvalds view](http://harmful.cat-v.org/software/c++/linus)

本文由 [**曼德普·辛格**](https://github.com/msdeep14) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。