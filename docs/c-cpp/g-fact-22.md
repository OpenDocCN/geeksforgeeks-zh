# 我们应该什么时候写自己的复制构造函数？

> 原文:[https://www.geeksforgeeks.org/g-fact-22/](https://www.geeksforgeeks.org/g-fact-22/)

C++ 编译器为类提供默认复制构造函数(和赋值运算符)。当我们不提供复制构造函数(和赋值操作符)的实现，并试图用同一类的已初始化对象初始化对象时，复制构造函数被调用，并在目标对象中逐个复制类的成员。

默认复制构造函数(和赋值操作符)的问题是——当我们有在运行时动态初始化的成员时，默认复制构造函数用动态分配内存的地址复制这个成员，而不是这个内存的真实副本。现在两个对象都指向相同的内存，并且一个对象中的变化反映在另一个对象中，此外，主要的灾难性影响是，当我们删除这个对象中的一个时，另一个对象仍然指向相同的内存，这将是悬空指针，并且内存泄漏也是这种方法的可能问题。

Hense，在这种情况下，我们应该总是编写自己的复制构造函数(和赋值操作符)。

来源:[http://www . fredosaurus . com/notes-CPP/OOP-condestructors/copy constructors . html](http://www.fredosaurus.com/notes-cpp/oop-condestructors/copyconstructors.html)