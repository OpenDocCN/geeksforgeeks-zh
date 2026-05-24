# realloc()

的使用

> 原文:[https://www.geeksforgeeks.org/g-fact-66/](https://www.geeksforgeeks.org/g-fact-66/)

动态分配的内存大小可以通过使用 realloc()来更改。

根据 C99 标准:

```cpp
void *realloc(void *ptr, size_t size);
```

*realloc 解除分配 ptr 指向的旧对象，并返回一个指向新对象的指针，该对象的大小由 size 指定。在解除分配之前，新对象的内容与旧对象的内容相同，直到新大小和旧大小中较小的一个。新对象中超出旧对象大小的任何字节都有不确定的值。* 

需要注意的是 **realloc()应该只用于动态分配的内存**。如果内存不是动态分配的，那么行为是未定义的。
例如，程序 1 演示了 realloc()的不正确使用，程序 2 演示了 realloc()的正确使用。

**程序 1:**

```cpp
#include <stdio.h>
#include <stdlib.h>
int main()
{
   int arr[2], i;
   int *ptr = arr;
   int *ptr_new;

   arr[0] = 10; 
   arr[1] = 20;      

   // incorrect use of new_ptr: undefined behaviour
   ptr_new = (int *)realloc(ptr, sizeof(int)*3);
   *(ptr_new + 2) = 30;

   for(i = 0; i < 3; i++)
     printf("%d ", *(ptr_new + i));

   getchar();
   return 0;
}
```

输出:
未定义的行为

 **节目 2:**

```cpp
#include <stdio.h>
#include <stdlib.h>
int main()
{
   int *ptr = (int *)malloc(sizeof(int)*2);
   int i;
   int *ptr_new;

   *ptr = 10; 
   *(ptr + 1) = 20;

   ptr_new = (int *)realloc(ptr, sizeof(int)*3);
   *(ptr_new + 2) = 30;
   for(i = 0; i < 3; i++)
       printf("%d ", *(ptr_new + i));

   getchar();
   return 0;
}
```

输出:
*10 20 30*

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。