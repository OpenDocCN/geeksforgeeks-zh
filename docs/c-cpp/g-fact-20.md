# C 中函数参数的求值顺序是什么？

> 原文:[https://www.geeksforgeeks.org/g-fact-20/](https://www.geeksforgeeks.org/g-fact-20/)

它依赖于 c 语言的编译器。依赖于副作用的评估顺序是不安全的。例如，像下面这样的函数调用可能在不同的编译器之间表现不同:

```cpp
void func (int, int);

int i = 2;
func (i++, i++);
```

不能保证(在 C 或 C++ 标准语言定义中)增量将以任何特定的顺序计算。任一增量都可能首先发生。func 可能得到参数“2，3 ”,也可能得到“3，2 ”,甚至“2，2”。

来源:[http://gcc.gnu.org/onlinedocs/gcc/Non_002dbugs.html](http://gcc.gnu.org/onlinedocs/gcc/Non_002dbugs.html)