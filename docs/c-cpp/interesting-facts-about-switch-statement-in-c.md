# C

中关于 switch 语句的有趣事实

> 原文:[https://www . geesforgeks . org/interest-facts-about-switch-in-c 语句/](https://www.geeksforgeeks.org/interesting-facts-about-switch-statement-in-c/)

先决条件–[开关语句在 C【](https://www.geeksforgeeks.org/switch-statement-cc/)】
开关是一个控制语句，允许一个值改变对执行的控制。

```cpp
// Following is a simple program to demonstrate syntax of switch.
#include <stdio.h>
int main()
{
   int x = 2;
   switch (x)
   {
       case 1: printf("Choice is 1");
               break;
       case 2: printf("Choice is 2");
                break;
       case 3: printf("Choice is 3");
               break;
       default: printf("Choice other than 1, 2 and 3");
                break;  
   }
   return 0;
} 
```

输出:

```cpp
Choice is 2
```

下面是一些关于 switch 语句的有趣事实。

***1)switch 中使用的表达式必须是整型(int、char 和 enum)。*** 任何其他类型的表情都是不允许的。

```cpp
// float is not allowed in switch
#include <stdio.h>
int main()
{
   float x = 1.1;
   switch (x)
   {
       case 1.1: printf("Choice is 1");
                 break;
       default: printf("Choice other than 1, 2 and 3");
                break;  
   }
   return 0;
} 
```

输出:

```cpp
 Compiler Error: switch quantity not an integer
```

在 Java 中，开关中也允许字符串(参见[这个](http://docs.oracle.com/javase/tutorial/java/nutsandbolts/switch.html))

***2)匹配案例之后的所有语句执行，直到到达 break 语句。**T3】*

```cpp
// There is no break in all cases
#include <stdio.h>
int main()
{
   int x = 2;
   switch (x)
   {
       case 1: printf("Choice is 1\n");
       case 2: printf("Choice is 2\n");
       case 3: printf("Choice is 3\n");
       default: printf("Choice other than 1, 2 and 3\n");
   }
   return 0;
} 
```

输出:

```cpp
Choice is 2
Choice is 3
Choice other than 1, 2 and 3
```

```cpp
// There is no break in some cases
#include <stdio.h>
int main()
{
   int x = 2;
   switch (x)
   {
       case 1: printf("Choice is 1\n");
       case 2: printf("Choice is 2\n");
       case 3: printf("Choice is 3\n");
       case 4: printf("Choice is 4\n");
               break;
       default: printf("Choice other than 1, 2, 3 and 4\n");
                break;
   }
   printf("After Switch");
   return 0;
}
```

输出:

```cpp
Choice is 2
Choice is 3
Choice is 4
After Switch
```

***3)默认块可以放在任何地方。*** 默认的位置不要紧，没有找到匹配的依然执行。

```cpp
// The default block is placed above other cases.
#include <stdio.h>
int main()
{
   int x = 4;
   switch (x)
   {
       default: printf("Choice other than 1 and 2");
                break;        
       case 1: printf("Choice is 1");
               break;
       case 2: printf("Choice is 2");
                break;
   }
   return 0;
}
```

输出:

```cpp
Choice other than 1 and 2
```

***4)标签中使用的积分表达式必须是常数表达式***

```cpp
// A program with variable expressions in labels
#include <stdio.h>
int main()
{
    int x = 2;
    int arr[] = {1, 2, 3};
    switch (x)
    {
        case arr[0]: printf("Choice 1\n"); 
        case arr[1]: printf("Choice 2\n");
        case arr[2]: printf("Choice 3\n");
    }
    return 0;
}
```

输出:

```cpp
Compiler Error: case label does not reduce to an integer constant
```

***5)以上案例编写的语句从不执行*** 切换语句后，控制转移到匹配案例，案例前编写的语句不执行。

```cpp
// Statements before all cases are never executed
#include <stdio.h>
int main()
{
   int x = 1;
   switch (x)
   {
       x = x + 1;  // This statement is not executed
       case 1: printf("Choice is 1");
               break;
       case 2: printf("Choice is 2");
                break;
       default: printf("Choice other than 1 and 2");
                break;                   
   }
   return 0;
} 
```

输出:

```cpp
Choice is 1
```

***6)两个案例标签不能有相同的值***

```cpp
// Program where two case labels have same value
#include <stdio.h>
int main()
{
   int x = 1;
   switch (x)
   {
       case 2: printf("Choice is 1");
               break;
       case 1+1: printf("Choice is 2");
                break;
   }
   return 0;
} 
```

输出:

```cpp
Compiler Error: duplicate case value
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论