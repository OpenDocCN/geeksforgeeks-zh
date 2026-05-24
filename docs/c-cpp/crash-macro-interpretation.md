# CRASH()宏–解释

> 原文:[https://www.geeksforgeeks.org/crash-macro-interpretation/](https://www.geeksforgeeks.org/crash-macro-interpretation/)

下面给出一小段来自开源项目的代码，

```cpp
#ifndef __cplusplus

typedef enum BoolenTag
{
   false,
   true
} bool;

#endif

#define CRASH() do { \
      ((void(*)())0)(); \
   } while(false)

int main()
{
   CRASH();
   return 0;
}
```

你能解释上面的代码吗？

很简单，下面给出了一个循序渐进的方法，

语句*而(false)* 仅用于测试目的。考虑以下操作，

```cpp
((void(*)())0)();
```

可以通过如下方式实现:

```cpp
0;                      /* literal zero */
(0); ( ()0 );                /* 0 being casted to some type */
( (*) 0 );              /* 0 casted some pointer type */
( (*)() 0 );            /* 0 casted as pointer to some function */
( void (*)(void) 0 );   /* Interpret 0 as address of function 
 taking nothing and returning nothing */
( void (*)(void) 0 )(); /* Invoke the function */
```

因此，给定的代码正在调用其代码存储在位置 0 的函数，换句话说，试图执行存储在位置 0 的指令。在有内存保护(MMU)的系统上，操作系统会抛出异常(分段错误)，而在没有这种保护的系统上(小型嵌入式系统)，它会执行，错误会进一步传播。

——[**文基**](http://www.linkedin.com/in/ramanawithu) 。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。