# C |结构&联盟|问题 5

> 原文:[https://www.geeksforgeeks.org/c-structure-union-question-5/](https://www.geeksforgeeks.org/c-structure-union-question-5/)

```cpp
#include<stdio.h> 
struct st 
{ 
    int x; 
    struct st next; 
}; 

int main() 
{ 
    struct st temp; 
    temp.x = 10; 
    temp.next = temp; 
    printf("%d", temp.next.x); 
    return 0; 
}
```

**(A)** 编译器错误
**(B)** 10
**(C)** 运行时错误
**(D)** 垃圾值

**答案:****(A)**

**解释:**一个结构不能包含自己类型的成员，因为如果允许，那么编译器就不可能知道这种结构的大小。虽然相同类型的指针可以是成员，因为所有类型的指针大小相同，编译器可以计算结构的大小

[这道题的小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)