# 如果循环到 C/C++ 中有符号和无符号的最大值会发生什么？

> 原文:[https://www . geesforgeks . org/if-what-if-loop-run-to-max-of-signed-and-unsigned-in-c/](https://www.geeksforgeeks.org/what-happens-if-loop-runs-till-maximum-of-signed-and-unsigned-in-c/)

让我们看看下面的 C/C++ 代码片段。

## C++

```cpp
// An Unsigned char example
#include <iostream>
using namespace std;
void fun1()
{
    unsigned char i;
    for (i = 0; i < 256; i++)
        cout << i << " ";
}

int main()
{
    fun1();
    return 0;
}

// This code is contributed by shubhamsingh10
```

## C

```cpp
// An Unsigned char example
#include<stdio.h>
void fun1()
{
    unsigned char i;
    for (i = 0; i < 256; i++)
        printf("%d ", i);
}

int main()
{
    fun1();
    return 0;
}
```

**Output:**

```cpp
 Infinite Loop 
```

**说明:**

我们知道字符变量的大小是 8 位或 1 字节。因此，通过十进制数的 2 进制表示，8 位中的最大数字是 11111111。这是因为 8 位无符号数的范围是从 0 到 2 <sup>8</sup> -1

现在(11111111)<sub>2</sub>=(255)<sub>10</sub>

如果我们从 0 开始将循环驱动到 255，它将在循环中执行该语句 256 次(包括 0 和 255 次)。当循环到达(255) <sub>10</sub> 时，在执行之后，变量“I”增加 1，即通过 2s 补码运算，

(11111111)<sub>2</sub>+(0000001)<sub>2</sub>=(0000000)<sub>10</sub>

注意:在这种情况下，结束进位被丢弃；因此最终递增的数字是 0，这导致循环的重新执行，因此循环运行无限次。因此，如果我们将无符号字符 I 的限制小于 255 而不是 256，就可以避免上述情况。

现在考虑下面的程序:

## C++

```cpp
// A signed char example
#include <iostream>
using namespace std;

void fun2()
{
    signed char i;
    for (i = 0; i < 128; i++)
        cout << i <<" ";
}

int main()
{
    fun2();
    return 0;
}

// This code is contributed by shubhamsingh10
```

## C

```cpp
// A signed char example
#include<stdio.h>

void fun2()
{
    signed char i;
    for (i=0; i<128; i++)
        printf("%d ",i);
}

int main()
{
    fun2();
    return 0;
}
```

Output on GCC (Undefined Behavior in Standard):

```cpp
 Infinite Loop  
```

带符号的字符范围从-2 <sup>7</sup> 到 2 <sup>7</sup> -1，因此如果限制为< 128，也是无限执行。

注意(127) <sub>10</sub> 的 2s 补码是(01111111) <sub>2</sub> 加 1 得到(10000000) <sub>2，</sub>从 2s 补码形式计算是–(128)<sub>10</sub>。

**那么如何从 0 循环到最大值(255 或 128 或任何其他最大值限制)？**
这样做的一种方式如下。

```cpp
// One way of looping till maximum of unsigned in C/C++
#include<stdio.h>
void fun1()
{
    unsigned char i = 0;
    do
    {
        printf("%d ", i);
        i++ ;
    }
    while (i > 0);
}
int main()
{
    fun1();
    return 0;
}
```

输出:*从 0 到 255 的数字*

```cpp
// One way of looping till maximum of signed in C/C++
// (Same as above except first statement)
#include<stdio.h>
void fun2()
{
    signed char i = 0;
    do
    {
        printf("%d ", i);
        i++ ;
    }
    while (i > 0);
}
int main()
{
    fun2();
    return 0;
}
```

GCC 中的输出:*从 0 到 127 的数字*

 ****注意:**在 C 语言中，有符号溢出是未定义的行为，因此上述解决方案可能不适用于所有有符号数的机器。此外，上面显示的带符号输出可能在所有机器上都不相同。对于无符号数字，这种行为定义得很好。**

以下是 C99 [中提到的](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1570.pdf)。

**关于无符号:**
涉及无符号操作数的计算永远不会溢出，因为不能由结果无符号整数类型表示的结果以比结果类型能够表示的最大值大一的数为模减少

**关于符号:**
*未定义行为的一个例子是整数溢出上的行为。*

本文由**普拉哈尔·马图尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论