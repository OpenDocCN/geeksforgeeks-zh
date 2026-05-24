# C |结构&联盟|问题 10

> 原文:[https://www.geeksforgeeks.org/c-structure-union-question-3/](https://www.geeksforgeeks.org/c-structure-union-question-3/)

```cpp
struct node 
{ 
   int i; 
   float j; 
}; 
struct node *s[10];
```

上面的 C 声明将“s”定义为(GATE CS 2000)
**(A)** 一个数组，其每个元素是指向类型节点
**(B)** 一个 2 字段的结构的指针，每个字段是指向 10 个元素的数组的指针
**(C)** 一个由 3 个字段组成的结构:一个整数、一个浮点数和一个 10 个元素的数组
**(D)** 一个数组，其中每个元素

**答案:****(A)**

**说明:**参考 C 中的[结构。](https://www.geeksforgeeks.org/structures-c/) [本题小考](https://www.geeksforgeeks.org/c-language-2-gq/structure-union-gq/)