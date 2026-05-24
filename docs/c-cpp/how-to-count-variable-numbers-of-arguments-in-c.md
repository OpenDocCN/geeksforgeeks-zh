# 如何计算 C 语言中变元的个数？

> 原文:[https://www . geeksforgeeks . org/如何计算 c 语言中的变量参数个数/](https://www.geeksforgeeks.org/how-to-count-variable-numbers-of-arguments-in-c/)

c 语言支持可变数量的参数。但是没有语言提供的方法来找出传递的参数总数。用户必须以下列方式之一来处理此问题:
1)通过将第一个参数作为参数计数传递。
2)通过将最后一个参数作为空(或 0)传递。
3)使用一些类似 printf(或 scanf)的机制，其中第一个参数有占位符用于其余参数。

下面是一个使用第一个参数 *arg_count* 保存其他参数计数的例子。

```cpp
#include <stdarg.h>
#include <stdio.h>

// this function returns minimum of integer numbers passed.  First 
// argument is count of numbers.
int min(int arg_count, ...)
{
  int i;
  int min, a;

  // va_list is a type to hold information about variable arguments
  va_list ap; 

  // va_start must be called before accessing variable argument list
  va_start(ap, arg_count); 

  // Now arguments can be accessed one by one using va_arg macro
  // Initialize min as first argument in list   
  min = va_arg(ap, int);

  // traverse rest of the arguments to find out minimum
  for(i = 2; i <= arg_count; i++) {
    if((a = va_arg(ap, int)) < min)
      min = a;
  }   

  //va_end should be executed before the function returns whenever
  // va_start has been previously used in that function 
  va_end(ap);   

  return min;
}

int main()
{
   int count = 5;

   // Find minimum of 5 numbers: (12, 67, 6, 7, 100)
   printf("Minimum value is %d", min(count, 12, 67, 6, 7, 100));
   getchar();
   return 0;
}
```

输出:
*最小值为 6*

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。