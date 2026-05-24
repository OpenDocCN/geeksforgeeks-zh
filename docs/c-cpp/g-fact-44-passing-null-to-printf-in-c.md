# 将空值传递给 C 中的 printf

> 原文:[https://www . geesforgeks . org/g-fact-44-passing-null-to-printf-in-c/](https://www.geeksforgeeks.org/g-fact-44-passing-null-to-printf-in-c/)

考虑下面的 C 代码片段。

```cpp
char* p = NULL;
printf("%s", p);

```

以上程序的输出应该是什么？
打印需要一个以“\0”结尾的字符数组(或字符串文字)，而它收到一个空指针。将空值传递给 printf 是未定义的行为。

根据第 7.1.4 节(C99 或 C11):库函数的使用

**如果函数的参数具有无效值(例如函数域之外的值，或程序地址空间之外的指针，或空指针，或当相应参数不是常量限定时指向不可修改的存储的指针)或具有可变参数数的函数不期望的类型(升级后)，则行为是未定义的。**

**一些编译器可能产生空值，而另一些则产生分段错误。GCC 打印(空)。**

```cpp
// Effect of passing null pointers to ( %s ) 
// printf in C
#include <stdio.h>

int main()
{
   char* p = NULL;
   printf( "%s", p);
   return 0;
}
```

**海湾合作委员会的产出:**

```cpp
(null)
```

**请注意，根据 C 标准，上述程序可能会导致未定义的行为。**

**本文由**阿迪亚查特吉**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论**