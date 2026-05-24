# C 语言编程标准

> 原文:[https://www . geesforgeks . org/c-编程-语言-标准/](https://www.geeksforgeeks.org/c-programming-language-standard/)

本文的思路是介绍 C 标准。

**当一个 C 程序在两个不同的编译器中产生不同的结果时该怎么办？**
例如，考虑以下简单的 C 程序。

## C

```cpp
void main() {  }
```

以上程序由于 main 的返回类型为 void，在 gcc 中失败，但在 Turbo C 中编译，我们如何判断它是否是合法的 C 程序？

考虑下面的程序作为另一个例子。它在不同的编译器中产生不同的结果。

## C

```cpp
#include<stdio.h>
int main()
{
    int i = 1;
    printf("%d %d %d\n", ++ i, i++, i);
    return 0;
}
```

```cpp
2 1 3 - using g++ 4.2.1 on Linux.i686
1 2 3 - using SunStudio C++ 5.9 on Linux.i686
2 1 3 - using g++ 4.2.1 on SunOS.x86pc
1 2 3 - using SunStudio C++ 5.9 on SunOS.x86pc
1 2 3 - using g++ 4.2.1 on SunOS.sun4u
1 2 3 - using SunStudio C++ 5.9 on SunOS.sun4u
```

来源: [Stackoverflow](http://stackoverflow.com/questions/376278/parameter-evaluation-order-before-a-function-calling-in-c)
哪个编译器是对的？
所有这类问题的答案都是 C 标准。在所有这样的情况下，我们需要看看 C 标准对这样的程序怎么说。

**什么是 C 标准？**
最新的 C 标准是 [ISO/IEC 9899:2011](http://en.wikipedia.org/wiki/C11_(C_standard_revision)) ，也叫 [C11](http://en.wikipedia.org/wiki/C11_(C_standard_revision)) 因为最终稿是 2011 年公布的。C11 之前有 [C99](http://en.wikipedia.org/wiki/C99) 。C11 最终稿在此提供。C 标准的完整历史见[本](http://en.wikipedia.org/wiki/C_(programming_language)#History)。

**我们能从 C 标准知道**所有程序的**行为吗？**
C 标准将许多 C 构造的一些行为保留为[未定义的](http://en.wikipedia.org/wiki/Undefined_behavior)，一些保留为[未指定的](http://en.wikipedia.org/wiki/Unspecified_behavior)，以简化规范并允许实现中的一些灵活性。例如，在 C 语言中，在任何自动变量被初始化之前使用它会产生未定义的行为，并且子表达式的求值顺序是未指定的。如果提交了这样的程序，这特别地释放了编译器去做任何最容易或最有效的事情。

**那么以上两个例子的结论是什么呢？**
让我们考虑第一个例子，即“void main() {}”，标准对 main()的原型说如下。

```cpp
The function called at program startup is named main. The implementation 
declares no prototype for this function. It shall be defined with a return 
type of int and with no parameters:
       int main(void) { /* ... */ }
or with two parameters (referred to here as argc and argv, though any names 
may be used, as they are local to the function in which they are declared):
       int main(int argc, char *argv[]) { /* ... */ }
or equivalent;10) or in some other implementation-defined manner.
```

所以返回类型 void 不符合标准，这是某些编译器允许的。

让我们谈谈第二个例子。请注意，C 标准中的以下语句列在“未指定的行为”下。

```cpp
The order in which the function designator, arguments, and 
subexpressions within the arguments are evaluated in a function 
call (6.5.2.2). 
```

**如何处理行为在标准中未定义或未指定的程序？**
作为一名程序员，使用行为未定义或未指定的编程构造从来都不是一个好主意，这样的程序应该总是被劝阻。这些程序的输出可能会随着编译器和/或机器而改变。
本文由**阿沛·拉提**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。