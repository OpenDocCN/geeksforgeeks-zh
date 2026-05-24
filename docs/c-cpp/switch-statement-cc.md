# C/c++ 中的开关语句

> 原文:[https://www.geeksforgeeks.org/switch-statement-cc/](https://www.geeksforgeeks.org/switch-statement-cc/)

Switch case 语句计算给定的表达式，并根据计算出的值(匹配某个条件)，执行与之关联的语句。基本上，它用于根据不同的条件(情况)执行不同的操作。

*   Switch case 语句遵循选择控制机制，并允许一个值改变对执行的控制。
*   它们是将一个变量与几个整数值进行比较的长 if 语句的替代。
*   switch 语句是一个多路分支语句。它提供了一种简单的方法，可以根据表达式的值将执行分派到代码的不同部分。

**语法:**

```cpp
switch (n)
{
    case 1: // code to be executed if n = 1;
        break;
    case 2: // code to be executed if n = 2;
        break;
    default: // code to be executed if n doesn't match any cases
}
```

**一些重要关键词:**

**1) Break:** 此关键字用于停止开关块内部的执行。它有助于终止开关块并将其断开。

**2)** **默认:**这个关键字用于指定在没有大小写匹配的情况下要执行的语句集。

> **注意:**有时候当**默认**没有放在 switch case 程序末尾的时候，我们要用 **break 语句**搭配默认 case。

**关于交换机案例陈述的要点:**

**1)** 开关中提供的表达式应得到一个**常量值**，否则无效。开关情况的一些有效表达式是，

```cpp
// Constant expressions allowed
switch(1+2+23)
switch(1*2+3%4)

// Variable expression are allowed provided
// they are assigned with fixed values
switch(a*b+c*d)
switch(a+b+c)
```

**2)不允许出现重复的事例值。**

**3)****默认语句是可选的**。即使 switch case 语句没有默认语句，
它也能毫无问题地运行。

**4)** 开关内部使用**中断语句来终止语句**序列。当到达 break 语句时，开关终止，控制流跳到开关语句之后的下一行。

**5)****中断语句是可选的**。如果省略，执行将继续到下一个案例。控制流将延续到后续案例，直到达到中断。

**6)** **允许 switch 语句嵌套**，也就是说你可以在另一个 switch 里面有 switch 语句。然而，应该避免嵌套的 switch 语句，因为它会使程序更加复杂，可读性更差。

**7)** 开关语句仅在检查条件下被**限制为整数值**。

**流程图:**

![switch-case-in-java](img/b3ac657711032acba364c8f60f2531f9.png)

**示例:**

## C

```cpp
// C program to demonstrate syntax of switch
#include <stdio.h>

// Driver Code
int main()
{
    int x = 2;
    switch (x) {
    case 1:
        printf("Choice is 1");
        break;
    case 2:
        printf("Choice is 2");
        break;
    case 3:
        printf("Choice is 3");
        break;
    default:
        printf("Choice other than 1, 2 and 3");
        break;
    }
    return 0;
}
```

## C++

```cpp
// C++ program  to demonstrate syntax of switch
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int x = 2;
    switch (x) {
    case 1:
        cout << "Choice is 1";
        break;
    case 2:
        cout << "Choice is 2";
        break;
    case 3:
        cout << "Choice is 3";
        break;
    default:
        cout << "Choice other than 1, 2 and 3";
        break;
    }
    return 0;
}
```

**Output**

```cpp
Choice is 2
```

**时间复杂度:** O(1)

**辅助空间:** O(1)

**必读:**

*   [关于 C](https://www.geeksforgeeks.org/interesting-facts-about-switch-statement-in-c/) 中开关情况的有趣事实
*   [C 语言中 Switch 语句案例标签的数据类型应该是什么？](https://www.geeksforgeeks.org/data-type-of-case-labels-of-switch-statement-in-c/)
*   [不使用 if 或 Switch 将单个数字打印为文字](https://www.geeksforgeeks.org/print-individual-digits-as-words-without-using-if-or-switch/)

本文由某个美国人撰写。如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。