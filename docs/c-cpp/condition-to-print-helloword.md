# 打印“HelloWord”的条件

> 原文:[https://www.geeksforgeeks.org/condition-to-print-helloword/](https://www.geeksforgeeks.org/condition-to-print-helloword/)

“条件”应该是什么，以便下面的代码片段打印两个 HelloWorld！

```cpp
      if  "condition"
          printf ("Hello");
      else
          printf("World"); 

```

**方法 1:**

```cpp
#include<stdio.h>
int main()
{
    if(!printf("Hello"))
        printf("Hello");
    else
        printf("World");
    getchar();
}        
```

**说明:** Printf 返回已成功打印的字符数。因此，以下解决方案也将有效

if (printf("Hello") < 0)或 if (printf("Hello") < 1)等

**方法二:使用[叉()](https://www.geeksforgeeks.org/fork-system-call/)**T0】

这种方法是阿拉文德·阿拉帕蒂贡献的。

如果你找到更多的解决方案，请评论。