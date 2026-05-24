# C 小测验–108 |问题 3

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-108-question-3/](https://www.geeksforgeeks.org/c-c-quiz-108-question-3/)

下列任何一项都可以用来声明单链表的节点和“NODEPTR nodePtr”可用于声明指向节点的指针

```cpp
/* First declaration */
typedef struct node
{
 int data;
 struct node *nextPtr;
}* NODEPTR;

/* Second declaration */
struct node
{
 int data;
 struct node * nextPtr;
};
typedef struct node * NODEPTR;
```

**(A)** 真
**(B)** 假

**回答:** **(A)**

**说明:**是。两者是等价的。上述任一声明都可以用于“NODEPTR nodePtr”。事实上，第一个是第二个的紧凑形式。

[本题小考](https://www.geeksforgeeks.org/c-quiz-108-gq/)