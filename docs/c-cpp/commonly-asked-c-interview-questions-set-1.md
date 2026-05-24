# 常见 C++ 面试问题|第 1 集

> 原文:[https://www . geesforgeks . org/common-question-c-interview-questions-set-1/](https://www.geeksforgeeks.org/commonly-asked-c-interview-questions-set-1/)

**C 和 C++ 有什么区别？**
**1)** C++ 是 C 的一种超集，大部分 C 程序除了极少数例外(见[本](https://www.geeksforgeeks.org/write-c-program-produce-different-result-c/)和[本](https://www.geeksforgeeks.org/write-c-program-wont-compiler-c/)外)在 C++ 中工作也是如此。
**2)** C 是过程编程语言，但 C++ 同时支持过程编程和面向对象编程。
**3)** 由于 C++ 支持面向对象编程，因此支持函数重载、模板、继承、虚函数、友元函数等特性。这些特性在 C 中是不存在的。
**(4)**c++ 在语言层面支持异常处理，在 C 中异常处理，是以传统的 if-else 风格完成的。
**5)** C++ 支持[引用](https://www.geeksforgeeks.org/references-in-c/) **，** C 不支持。
**6)** 在 C 语言中，主要使用 scanf()和 printf()进行输入/输出。C++ 主要使用流来执行输入和输出操作。cin 是标准输入流，cout 是标准输出流。

还有很多不同之处，以上是主要区别的列表。

**引用和指针有什么区别？**
引用和指针都可以用来改变一个函数在另一个函数中的局部变量。当作为参数传递给函数或从函数返回时，这两种方法都可以用来节省大对象的复制，从而提高效率。
尽管有上述相似之处，但引用和指针之间存在以下差异。

*引用不如指针*
1)一旦创建了引用，以后就不能再引用另一个对象；无法重新拔插。这通常是通过指针来完成的。
2)引用不能为空。指针通常为空，表示它们没有指向任何有效的东西。
3)引用在声明时必须初始化。指针没有这样的限制

由于上述限制，C++ 中的引用不能用于实现链表、树等数据结构。在 Java 中，引用没有上述限制，可以用来实现所有的数据结构。Java 中引用功能更强大是 Java 不需要指针的主要原因。
*引用更安全更容易使用:*
1)更安全:由于引用必须初始化，像野指针这样的野引用不太可能存在。仍然有可能存在不引用有效位置的引用(参见下面练习中的问题 5 和 6)
2)更容易使用:引用不需要解引用运算符来访问值。它们可以像普通变量一样使用。&'仅在申报时需要操作员。此外，可以使用点运算符('.'来访问对象引用的成员)，与需要箭头运算符(- >)来访问成员的指针不同。

**什么是虚函数——写一个例子？**
[虚函数](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/)与继承一起使用，它们是根据被指向或引用的对象的类型来调用的，而不是根据指针或引用的类型来调用的。换句话说，虚函数在运行时被延迟解析。virtual 关键字用于使函数虚拟化。

编写一个运行时多态的 C++ 程序(使用虚函数)
需要做以下事情 1)一个基类和一个派生类。
2)基类和派生类中同名的函数。
3)基类类型的指针或引用，指向或引用派生类的对象。

例如，在下面的程序中，bp 是 Base 类型的指针，但是对 bp 的调用->show()调用派生类的 show()函数，因为 bp 指向派生类的对象。

## C++

```cpp
#include<iostream>
using namespace std;

class Base {
public:
    virtual void show() { cout<<" In Base \n"; }
};

class Derived: public Base {
public:
    void show() { cout<<"In Derived \n"; }
};

int main(void) {  
    Base *bp = new Derived;    
    bp->show();  // RUN-TIME POLYMORPHISM
    return 0;
}
```

**输出:**

```cpp
In Derived
```

**这个指针是什么？**
[“this”指针](https://www.geeksforgeeks.org/this-pointer-in-c/)作为隐藏参数传递给所有非静态成员函数调用，并作为所有非静态函数体内的局部变量可用。“this”指针是一个常量指针，保存当前对象的内存地址。“this”指针在静态成员函数中不可用，因为静态成员函数可以在没有任何对象(带有类名)的情况下调用。

**我们可以做“删除这个”吗？**
见[https://www.geeksforgeeks.org/delete-this-in-c/](https://www.geeksforgeeks.org/delete-this-in-c/)

**什么是 VTABLE 和 VPTR？**
vtable 是一个函数指针表。它是按类维护的。
vptr 是指向 vtable 的指针。它是按对象维护的(参见这个例子)。
编译器在两个地方增加了额外的代码来维护和使用 vtable 和 vptr。
1)每个构造函数中的代码。这段代码设置正在创建的对象的 vptr。这段代码将 vptr 设置为指向该类的 vtable。
2)带有多态函数调用的代码(如上述代码中的 bp- > show())。无论在哪里进行多态调用，编译器都会插入代码，首先使用基类指针或引用来查找 vptr(在上面的示例中，由于被指向或引用的对象是派生类型的，因此会访问派生类的 vptr)。一旦提取了 vptr，就可以访问派生类的 vtable。使用 vtable，可以访问和调用派生类函数 show()的地址。

你可能还喜欢:

*   在 C++ 上练习[小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)
*   C/C++ [文章](https://www.geeksforgeeks.org/category/c-puzzles/)

我们将很快覆盖更多的 C++。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。