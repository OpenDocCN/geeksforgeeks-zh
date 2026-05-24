# 什么是近、远、巨指针？

> 原文:[https://www . geeksforgeeks . org/什么是远近巨大指针/](https://www.geeksforgeeks.org/what-are-near-far-and-huge-pointers/)

这些都是 MS DOS 时代 16 位英特尔架构中使用的一些老概念，已经没什么用了。

**近指针**用于在 16 位机器上存储当前段内的 16 位地址。限制是我们一次只能访问 64kb 的数据。

**远指针**通常是 32 位，可以访问当前段之外的内存。为此，编译器分配一个段寄存器来存储段地址，然后分配另一个寄存器来存储当前段内的偏移量。

和远指针一样，**巨大指针**也是典型的 32 位，可以访问段外。在远指针的情况下，段是固定的。在远指针中，线段部分不能修改，但在巨指针中可以修改

有关更多详细信息，请参见以下链接。

[http://www . answers . com/Q/What _ are _ near _ far _ 和 _ 巨大 _pointers_in_C](http://www.answers.com/Q/What_are_near_far_and_huge_pointers_in_C)

[https://www . quora . com/C-c++ 中的近-远-巨大指针的区别是什么](https://www.quora.com/What-is-the-difference-between-near-far-huge-pointers-in-C-C++)

[http://stackoverflow . com/questions/8727122/解释 c 语言中的远近和巨大指针的区别](http://stackoverflow.com/questions/8727122/explain-the-difference-between-near-far-and-huge-pointers-in-c)

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论