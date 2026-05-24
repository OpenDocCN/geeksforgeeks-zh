# C |动态内存分配|问题 8

> 原文:[https://www . geesforgeks . org/c-dynamic-memory-allocation-question-8/](https://www.geeksforgeeks.org/c-dynamic-memory-allocation-question-8/)

考虑下面的程序，I、j 和 k 存储在内存的什么地方？

```cpp
int i;
int main()
{
    int j;
    int *k = (int *) malloc (sizeof(int));
}
```

**(A)** i、j 和*k 存储在栈段
**(B)** i 和 j 存储在栈段。*k 存储在堆上。
**(C)** i 存储在数据段的 BSS 部分，j 存储在栈段。*k 存储在堆上。
**(D)** j 存储在数据段的 BSS 部分，I 存储在栈段。*k 存储在堆上。

**回答:****(C)**

**说明:** i 是全局变量，未初始化，所以存储在 Data Segment(http://en.wikipedia.org/wiki/.bss)的 BSS 部分

j 在 main()中是本地的，因此它存储在堆栈帧(http://en.wikipedia.org/wiki/Call_stack)中

*k 是动态分配的，因此它存储在堆段上。

有关更多详细信息，请参见下面的文章。

[C 程序的内存布局](https://www.geeksforgeeks.org/memory-layout-of-c-program/)

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/dynamic-memory-allocation-gq/)