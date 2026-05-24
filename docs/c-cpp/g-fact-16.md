# 变量在 C 语言中的作用域是静态的还是动态的？

> 原文:[https://www.geeksforgeeks.org/g-fact-16/](https://www.geeksforgeeks.org/g-fact-16/)

在 C 语言中，变量总是[静态(或词汇)范围的](http://en.wikipedia.org/wiki/Scope_%28programming%29#Lexical_scoping)，即变量的绑定可以由程序文本决定，并且独立于运行时函数调用堆栈。

例如，下面程序的输出为 0，即 f()返回的值不依赖于调用它的人。f()总是返回全局变量 x 的值。

```cpp
# include <stdio.h>

int x = 0;
int f()
{
   return x;
}
int g()
{
   int x = 1;
   return f();
}
int main()
{
  printf("%d", g());
  printf("\n");
  getchar();
}
```

参考文献:
[http://en.wikipedia.org/wiki/Scope_%28programming%29](http://en.wikipedia.org/wiki/Scope_%28programming%29)