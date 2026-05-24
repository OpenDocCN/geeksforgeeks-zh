# C 小测验–108 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-108-question-2/](https://www.geeksforgeeks.org/c-c-quiz-108-question-2/)

下列任何一项都可以用来声明单链表的节点。如果我们使用第一个声明，“struct node * nodePtr”将用于声明指向节点的指针。如果我们使用第二个声明“NODEPTR nodePtr”可用于声明指向节点的指针。

```cpp
/* First declaration */
struct node {
int data;
struct node * nextPtr;
};

/* Second declaration */
typedef struct node{
int data;
NODEPTR nextPtr;
} * NODEPTR;
```

**(A)**TRUE
**(B)**FALSE

**答案:** **(B)**

**说明:**这个 *typedef* 用法不正确。基本上，我们在应用 *typedef* 本身的时候，还不能在内部使用被 typedef 化的数据类型。这里，NODEPTR 还有待定义(即 typedef-ed)，我们在结构本身内部使用 NODEPTR。

[本题小考](https://www.geeksforgeeks.org/c-quiz-108-gq/)