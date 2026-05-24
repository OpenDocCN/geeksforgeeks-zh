# 预定义的标识符 __ 函数 _ _ 在 C 中

> 原文:[https://www . geesforgeks . org/predefined-identifier-_ _ func _ _-c/](https://www.geeksforgeeks.org/predefined-identifier-__func__-c/)

在我们开始讨论 *__func__* 之前，让我们编写一些代码片段并预测输出:

## C

```cpp
#include <stdio.h>

int main()
{
   printf("%s",__func__);
   return 0;
}
```

会不会因为没有定义变量 *__func__* 而导致编译错误？嗯，到目前为止你应该已经猜到了，它不会给出任何编译错误，并且会打印 **main** ！

c 语言标准(即 C99 和 C11)在第 6.4.2.2 条中定义了预定义的标识符，如下所示:

”*标识符 __func__ 应由翻译器隐式声明，就像紧接在每个函数定义的左括号之后的声明*
*static const char _ _ func _ _[]=“函数名”；*
*出现了，其中函数名是词汇封闭函数的名字。*”

这意味着 C 编译器在每个函数中隐式添加 *__func__* ，以便在该函数中使用它来获取函数名。为了更好地理解它，让我们编写以下代码:

## C

```cpp
#include <stdio.h>
void foo(void)
{
   printf("%s",__func__);
}
void bar(void)
{
   printf("%s",__func__);
}

int main()
{
   foo();
   bar();
   return 0;
}
```

它将输出为 **foobar** 。这个预定义标识符的一个用例可能是记录一个大程序的输出，程序员可以使用 *__func__* 来获取当前函数，而不是显式地提到完整的函数名。如果我们再定义一个名为 *__func__* 的变量，会发生什么

## C

```cpp
#include <stdio.h>

int __func__ = 10;
int  main()
{
   printf("%d",__func__);
   return 0;
}
```

既然 C 标准说编译器为每个函数隐式定义了 *__func__* 作为函数名，我们就不应该首先定义 *__func__* 。你可能会得到错误，但是如果有人明确定义了*_ _ 函数 __* ，C 标准会说“未定义的行为”。

为了结束对预定义标识符 *__func__* 的讨论，让我们也提到预定义宏(如 __FILE__ 和 __LINE__ 等)。)基本上，C 标准第 6.10.8 条提到了几个预定义的宏，其中 *__FILE__* 和 *__LINE__* 与此相关。

值得一看以下代码片段的输出:

## C

```cpp
#include <stdio.h>

int main()
{
   printf("In file:%s, function:%s() and line:%d",__FILE__,__func__,__LINE__);

   return 0;
}
```

我们不解释输出，而是留给你去猜测和理解 *__FILE__* 和 *__LINE__* 的作用！
如果觉得以上有用，请做 Like/Tweet/G+1。此外，请给我们留下进一步澄清或信息的评论。我们很乐意帮助和学习🙂