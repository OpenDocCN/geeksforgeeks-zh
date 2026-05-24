# C |动态内存分配|问题 3

> 原文:[https://www . geesforgeks . org/c-dynamic-memory-allocation-question-3/](https://www.geeksforgeeks.org/c-dynamic-memory-allocation-question-3/)

输出？

```cpp
# include<stdio.h>
# include<stdlib.h>

void fun(int *a)
{
    a = (int*)malloc(sizeof(int));
}

int main()
{
    int *p;
    fun(p);
    *p = 6;
    printf("%d\n",*p);
    return(0);
}
```

**(A)** 可能不工作
**(B)** 工作打印 6

**回答:** **(A)**

**说明:**程序无效。尝试替换“int * p；”带有“int * p = NULL”并且它将尝试取消引用空指针。
这是因为 fun()会对指针进行复制，所以在调用 malloc()时，是将复制的指针设置到内存位置，而不是 p. p 在调用 fun()前后指向随机内存，当你去引用它时，它会崩溃。
如果你想从函数中给指针增加内存，你需要传递指针的地址(即。双指针)。