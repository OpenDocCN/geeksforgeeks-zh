# C |指针基础|问题 1

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-1/](https://www.geeksforgeeks.org/c-pointers-question-1/)

以下程序的输出是什么？

```cpp
# include <stdio.h>
void fun(int x)
{
    x = 30;
}

int main()
{
  int y = 20;
  fun(y);
  printf("%d", y);
  return 0;
}
```

**(A)**30
**(B)**20
**(C)**编译器错误
**(D)** 运行时错误

**答案:****(B)**

**解释:**参数总是通过 C 中的值传递的，因此，在上面的代码中，y 的值没有使用 fun()函数进行修改。那么我们如何修改一个函数的局部变量在另一个函数中的值呢？指针就是解决这类问题的方法。使用指针，我们可以在另一个函数中修改一个函数的局部变量。见下一个问题。
注意在 c 语言中一切都是按值传递的，我们只利用指针得到按引用传递的效果。