# Veritas 面试体验 | 第二集（校园）

> 原文：[https://www.geeksforgeeks.org/veritas-interview-experience-set-2-campus/](https://www.geeksforgeeks.org/veritas-interview-experience-set-2-campus/)

**Veritas** 来我院进行校园招聘。反恐委员会出价 9.26 LPA。共有 105 名候选人有资格参加招聘考试。选拔过程包括一次能力测试、两次技术面试和一次人力资源面试。

## 第一轮：资质与技术测试

能力测试在 HackerRank 上进行。
它有 20 个基于 CS 概念、C/C++ 输出题、OOPS 概念（构造函数、继承、重载、覆盖）等的 MCQs。
还有两个编码问题：
- 问题 1：编写一个函数来检测链表中的循环。返回“是”或“否”。[检测链表中的循环](https://www.geeksforgeeks.org/detect-loop-in-a-linked-list/)
- 问题 2：编写一个函数删除链表中所有包含大于 `k` 值的数据的节点，返回头节点。

我的方法是：
1. 使用两个指针 `prev` 和 `curr` 遍历链表。
2. 当 `curr` 值大于 `k` 时，使 `prev->next` 指向 `curr->next`。
3. 删除当前节点。
4. 使新 `curr` 指向 `prev->next`。
5. 重复直到 `curr` 不为空。

还有一些边缘案例需要覆盖。

第一回合很容易。105 名学生中约有 30 名入围了技术面试。所有轻松通过这两个编码问题所有测试用例的人都被选中，很少部分提交的人也被选中。

## 第二轮：技术面试

- 问题 1：说说你自己。（只是走个形式，面试官在想要问的问题）
- 问题 2：在以下科目中给自己打 10 分：C、[C++](https://www.geeksforgeeks.org/c-plus-plus/)、OOPS、[OS](https://www.geeksforgeeks.org/operating-systems/)、系统编程/编译器设计、质量测试。
- 问题 3：[存储类](https://www.geeksforgeeks.org/storage-classes-in-c/)
- 问题 4：[堆栈和堆内存表示](https://www.geeksforgeeks.org/memory-layout-of-c-program/)
- 问题 5：深度轰击 OOPS 概念：继承、访问说明符、私有、公共保护继承的区别、输出问题。
- 问题 6：深度指针。非常注意语法：解引用、双指针。
- 问题 7：[这个关于三元搜索的问题](https://www.geeksforgeeks.org/binary-search-preferred-ternary-search/)
- 问题 8：[链表中的中间元素](https://www.geeksforgeeks.org/write-a-c-function-to-print-the-middle-of-the-linked-list/)
- 问题 9：讲解所有你知道的排序技巧。
- 问题 10：编写[插入排序](https://www.geeksforgeeks.org/insertion-sort/)的代码。
- 问题 11：[合并排序链表](https://www.geeksforgeeks.org/merge-sort-for-linked-list/)

## 第三轮：技术面试 - 二

- 问题 1：说说你自己。
- 问题 2：项目讨论。
- 问题 3：操作系统中的引导过程。
- 问题 4：Linux 命令。
- 问题 5：[进程 vs 线程](https://practice.geeksforgeeks.org/problems/processes-vs-threads?qa-rewrite=42/process-vs-threads)
- 问题 6：[互斥 vs 信号量](https://www.geeksforgeeks.org/mutex-vs-semaphore/)
- 问题 7：[OS 中分页](https://www.geeksforgeeks.org/operating-system-paging/)深度。
- 问题 8：分页和分段的实际使用。
- 问题 9：[在一个句子](https://www.geeksforgeeks.org/reverse-words-in-a-given-string/)中颠倒单词，不使用任何额外的空格。

## 第四轮：HR 面试

- 问题 1：说说你自己。
- 问题 2：课外活动。
- 问题 3：为什么是 Veritas？
- 问题 4：哪些领域需要改进？
- 问题 5：5 年后你在哪里看自己？
- 问题 6：优势和劣势。

一些比较典型的 HR 问题。
然后他们说“你被选中了”。

所有进入人力资源轮的学生都被选中了。总的来说，从 30 个中选出了 7 个。

本文由 **维伦德拉·辛格·拜斯** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。