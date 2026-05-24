# C 小测验–108 |问题 1

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-108-question-1/](https://www.geeksforgeeks.org/c-c-quiz-108-question-1/)

在下面的语句中，ptr1 和 ptr2 是指向 int 的未初始化指针，即它们指向某个随机地址，该地址可能是也可能不是有效地址。

```cpp
int* ptr1, ptr2;
```

**(A)** 真
**(B)** 假

**答案:** **(B)**

**解释:**即使*被放置得更靠近 *int* ，*将仅与 ptr1 相关联，而不与 ptr2 相关联。意思是“int* ptr1”等于“int *ptr1”。这就是为什么只有 ptr1 是指向 int 的未初始化指针。基本上，虽然 ptr1 和 ptr2 都是未初始化的变量，但是 ptr1 是指向 int 的指针，而 ptr2 是 int 类型的变量。如果我们真的想让两个变量都成为指针，我们需要把它们称为“int *ptr1，* ptr2”

[本题小考](https://www.geeksforgeeks.org/c-quiz-108-gq/)