# C |集合 1 中的序列点

> 原文:[https://www.geeksforgeeks.org/sequence-points-in-c-set-1/](https://www.geeksforgeeks.org/sequence-points-in-c-set-1/)

在这篇文章中，我们将试图涵盖许多模糊的问题，如以下。

猜测以下程序的输出。

```cpp
// PROGRAM 1
#include <stdio.h>
int f1() { printf ("Geeks"); return 1;}
int f2() { printf ("forGeeks"); return 1;}
int main() 
{ 
  int p = f1() + f2();  
  return 0; 
}

// PROGRAM 2
#include <stdio.h>
int x = 20;
int f1() { x = x+10; return x;}
int f2() { x = x-5;  return x;}
int main()
{
  int p = f1() + f2();
  printf ("p = %d", p);
  return 0;
}

// PROGRAM 3
#include <stdio.h>
int main()
{
   int i = 8;
   int p = i++*i++ ;
   printf("%d\n", p);
}
```

以上所有程序的输出都是[未定义](http://en.wikipedia.org/wiki/Undefined_behavior)或[未指定](http://en.wikipedia.org/wiki/Unspecified_behavior)。不同编译器和不同机器的输出可能不同。这就像问未定义的自动变量的值。

程序 1 中未定义行为的原因是，运算符“+”没有为其操作数定义标准的求值顺序。可以先执行 f1()或 f2()。因此输出可能是“极客伪造”或“伪造”。
类似于运算符“+”，其他大多数类似的运算符如“-”、“/”、“*”、按位 AND &、按位 OR |，..etc 没有标准定义的操作数求值顺序。

对表达式的评估也可能产生副作用。例如，在上述程序 2 中，p 的最终值是不明确的。根据表达式求值的顺序，如果 f1()先执行，p 的值将是 55，否则是 40。

程序 3 的输出也是未定义的。可能是 64，72，也可能是别的什么。子表达式 i++ 会产生副作用，它会修改 I 的值，这将导致未定义的行为，因为 I 也在同一个表达式的其他地方被引用。

与上述情况不同的是，*在被称为[序列点](http://en.wikipedia.org/wiki/Sequence_point)的执行序列中的特定点上，先前评估的所有副作用都保证是完整的*。一个[序列点](http://en.wikipedia.org/wiki/Sequence_point)定义了计算机程序执行中的任意一点，在该点上保证先前评估的所有副作用都已经被执行，并且后续评估的副作用还没有被执行。以下是 C 标准中列出的顺序点:

**—下列运算符的第一个操作数的结尾:**
a)逻辑 AND & &
b)逻辑 OR ||
c)条件？
d)逗号、

例如，以下程序的输出保证在所有编译器/机器上都是“GeeksforGeeks”。

```cpp
// Following 3 lines are common in all of the below programs
#include <stdio.h>
int f1() { printf ("Geeks"); return 1;}
int f2() { printf ("forGeeks"); return 1;}

// PROGRAM 4
int main() 
{ 
   // Since && defines a sequence point after first operand, it is 
   // guaranteed that f1() is completed first.
   int p = f1() && f2();  
   return 0; 
}

// PROGRAM 5
int main()
{
   // Since comma operator defines a sequence point after first operand, it is
   // guaranteed that f1() is completed first.
  int p = (f1(), f2());
  return 0;
}

// PROGRAM 6
int main() 
{ 
   // Since ? operator defines a sequence point after first operand, it is 
   // guaranteed that f1() is completed first.
  int p = f1()? f2(): 3;  
  return 0; 
}
```

**——一个完整表达的结尾。此类别包括以下表达式语句**
a)任何以分号结束的完整语句，如“a = b；”
b)返回语句
c)if、switch、while 或 do-while 语句的控制表达式。
d)for 语句中的所有三个表达式。

上面的序列点列表是部分的。我们将在下一篇关于序列点的文章中介绍所有剩余的序列点。

参考文献:
[【http://en.wikipedia.org/wiki/Sequence_point】](http://en.wikipedia.org/wiki/Sequence_point)
[【http://c-faq.com/expr/seqpoints.html】](http://c-faq.com/expr/seqpoints.html)
[http://msdn . Microsoft . com/en-us/library/d45c 7a 5d(v = vs . 110)。aspx](http://msdn.microsoft.com/en-us/library/d45c7a5d(v=vs.110).aspx)
[http://www.open-std.org/jtc1/sc22/wg14/www/docs/n925.htm](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n925.htm)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。