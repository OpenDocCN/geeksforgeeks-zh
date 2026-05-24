# 为什么 C++ 是部分面向对象语言？

> 原文:[https://www . geesforgeks . org/c-部分面向对象语言/](https://www.geeksforgeeks.org/c-partially-object-oriented-language/)

面向对象编程的基本特征是**继承**、**多态**和**封装**。任何完全支持这些特性编程语言都是完整的面向对象编程语言，而任何支持所有这三个特性但不完全支持所有特性的语言都是部分面向对象编程语言。

**继承**用来提供代码可重用的概念。
**多态性**使得语言能够在不同的情况下执行不同的任务。
**封装**使得数据抽象(数据的安全性或隐私性)成为可能。在面向对象编程语言中，封装是借助一个**类**来实现的。

**以下是 C++ 被称为部分或半面向对象语言的原因:**

1.  **Main 函数在类**之外:C++ 支持面向对象编程，但 OO 不是语言固有的。你可以编写一个有效的、编码良好的、风格极佳的 C++ 程序，而无需使用一次对象。
    在 C++ 中，main 函数是强制的，它首先执行，但是它**驻留在类**之外，我们从那里创建对象。因此，在这里类的创建变成了**可选的**，我们可以不用类来编写代码。

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    cout << "Hello World";
    return 0;
}
```

而在 JAVA 中，主函数首先被执行，它在类中被设计，类是强制的。所以，不上课我们什么都做不了。为了做与上面相同的事情，我们需要创建一个类作为:

```cpp
class hello
{
    public static void main(String args[])
    {
        System.out.println("Hello World");
    }
}
```

*   **Concept of Global variable :** In C++, we can declare a variable globally, which can be accessible from anywhere and hence, it does not provides complete privacy to the data as no one can be restricted to access and modify those data and so, it provides encapsulation partially whereas In JAVA, we can declare variable inside class only and we can provide access specifier to it.

    ```cpp
    #include <iostream>
    using namespace std;

    // Global variable declaration:
    int g = 50;

    int main () 
    {
        // global variable g
        cout << g;

       // Local variable g
       g = 20;
       cout << g;

       return 0;
    }
    ```

    输出:

    ```cpp
    50 20 
    ```

    所以，在 JAVA 中，基本上每个数据都被用户明确询问**是否应该被访问**。

    *   **Availability of [Friend function](https://www.geeksforgeeks.org/friend-class-function-cpp/):** Friend Class A friend class can access private and protected members of other class in which it is declared as friend. It is sometimes useful to allow a particular class to access private members of other class.
    Therefore, again the Object oriented features can be violated by C++.

     **相关文章:** [为什么 Java 不是纯粹的面向对象语言？](https://www.geeksforgeeks.org/java-not-purely-object-oriented-language/)

    本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。