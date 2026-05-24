# C |数据类型|问题 1

> 原文:[https://www.geeksforgeeks.org/c-data-types-question-1/](https://www.geeksforgeeks.org/c-data-types-question-1/)

预测后续程序的输出。假设数字以 2 的补码形式存储。

```cpp
#include<stdio.h> 
int  main() 
{ 
   unsigned int x = -1; 
   int y = ~0; 
   if (x == y) 
      printf("same"); 
   else
      printf("not same"); 
   return 0; 
}
```

**(A)** 相同
**(B)** 不相同

**回答:** **(A)**

**说明:** -1 和~0 本质上具有相同的位模式，因此 x 和 y 必须相同。在比较中，y 被提升为无符号，并与 x 进行比较(提升规则见[本](http://publib.boulder.ibm.com/infocenter/comphelp/v101v121/index.jsp?topic=/com.ibm.xlcpp101.aix.doc/language_ref/cplr066.html))。结果是“一样”。但是，当解释为有符号和无符号时，它们的数值会有所不同。x 是 MAXUNIT，y 是-1。因为 y 也有%u，所以输出将是 MAXUNT 和 MAXUNT。

[本题竞猜](https://www.geeksforgeeks.org/c-language-2-gq/data-types-gq/)