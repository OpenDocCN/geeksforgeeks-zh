# 如何在 C 语言中不使用循环和递归打印一个数字 100 次？

> 原文:[https://www . geesforgeks . org/print-number-100-times-不使用循环-递归-c/](https://www.geeksforgeeks.org/print-number-100-times-without-using-loop-recursion-c/)

使用循环或递归方法可以解决这个问题，但是如果两者都不允许呢？

一个简单的解决方法是在 cout 语句中把数字写 100 遍。更好的解决方案是使用#define 指令([宏扩展](https://www.geeksforgeeks.org/c-language-2-gq/macro-preprocessor-gq/) )

```cpp
// CPP program to print "1" 100 times.

// Prints 1 only once
#define a cout<<"1"<<endl;

// Puts "a" 10 times
#define b a a a a a a a a a a

// Puts "b" 10 times
#define c b b b b b b b b b b

int main()
{
  c;
  return 0;
}
```

输出:100 乘以 1。

本文由 **[阿迪蒂亚·拉赫查](https://www.linkedin.com/in/aditya-rakhecha-34a597129/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。