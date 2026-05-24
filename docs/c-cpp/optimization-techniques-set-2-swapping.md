# 优化技术|集合 2(交换)

> 原文:[https://www . geesforgeks . org/optimization-technologies-set-2-swapping/](https://www.geeksforgeeks.org/optimization-techniques-set-2-swapping/)

如何互换两个变量？

这个问题可能看起来很傻，既不古怪。参见下面这段代码来交换两个整数([异或交换](http://en.wikipedia.org/wiki/XOR_swap_algorithm))，

```cpp
void myswap(int *x, int *y)
{
   if (x != y)
   {
      *x^=*y^=*x^=*y;
   }
}
```

乍一看，我们可能认为代码没有问题。然而，当被提示选择异或交换逻辑背后的原因时，这个人毫无头绪。或许任何 ***的交换式*** 操作都可以满足某些角落情况的需要。

避免在生产软件中使用花哨的代码片段。它们创造了运行时惊喜。我们可以观察上面代码

1.  The following comments, the code behavior is undefined. * x = * y = * x = * y's statement; Modify the variable several times without any [sequence point](http://en.wikipedia.org/wiki/Sequence_point) .
2.  When executed on a processor with pipeline architecture, it will create [pipeline](http://en.wikipedia.org/wiki/Instruction_pipeline) pause.
3.  The compiler cannot take advantage of the optimized swap operation. Some processors will provide a single instruction to exchange two variables. When we choose the standard library function, the library has more chances to be optimized. Even the compiler can recognize such standard functions and generate the best code.
4.  Code readability is poor. It is very important to write maintainable code.

感谢**文基**撰写以上文章。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。