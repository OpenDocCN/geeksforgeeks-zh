# C |指针基础|第 12 题

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-14/](https://www.geeksforgeeks.org/c-pointers-question-14/)

考虑这个 C 代码来交换两个整数和后面的这五个语句:

```cpp
void swap(int *px, int *py) 
{ 
   *px = *px - *py; 
   *py = *px + *py; 
   *px = *py - *px; 
}
```

S1:将生成编译错误
S2:可能会在运行时根据传递的参数生成分段错误
S3:正确地对引用存储在进程可访问的内存位置中的整数的所有输入指针执行交换过程
S4:对一些但不是所有有效的输入指针正确地执行交换过程
S5:可能会加减整数和指针。

**(A)**S1
T3】(B)S2 和 S3
T6】(C)S2 和 S4

**(D)** S2 和 S5

**回答:** **(C)**

**解释:** S2:如果指针 px 或 py 处的值为常量，或者 px 或 py 指向无效的内存位置，则可能会生成分段错误
S4:可能不会对所有输入都有效，因为可能会发生算术溢出