# c++ 中的平凡类

> 原文:[https://www.geeksforgeeks.org/trivial-classes-c/](https://www.geeksforgeeks.org/trivial-classes-c/)

当 C++ 中的类或结构具有编译器提供的或显式默认的特殊成员函数时，它就是一个普通类型。它占据了一个连续的内存区域。它可以有具有不同访问说明符的成员。

平凡类型有平凡的默认构造函数、平凡的复制构造函数、平凡的复制赋值运算符和平凡的析构函数。在每种情况下，平凡意味着构造函数/运算符/析构函数不是用户提供的，并且属于这样的类:

*   There is no virtual function or virtual base class,
*   There is no base class with corresponding nontrivial constructor/operator/destructor.
*   There is no data member of class type with corresponding nontrivial constructor/operator/destructor.

以下示例显示了琐碎类型:

```cpp
/*Since there are no explicit constructors,
there exists a default constructor*/
struct Trivial {
    int i;

private:
    int j;
};

/* In Trivial2 structure, the presence of the 
   Trivial2(int a, int b) constructor requires
   that you provide a default constructor. For 
   the type to qualify as trivial, we must  
   explicitly default that constructor.*/
struct Trivial2 {
    int i;
    Trivial2(int a, int b)
    {
        i = a;
    }
    Trivial2() = default;
};
```

**参考:**https://msdn.microsoft.com/en-us/library/mt767760.aspx

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。