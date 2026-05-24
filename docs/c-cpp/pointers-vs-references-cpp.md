# c++ 中的指针与引用

> 原文:[https://www.geeksforgeeks.org/pointers-vs-references-cpp/](https://www.geeksforgeeks.org/pointers-vs-references-cpp/)

先决条件:[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)、[参考](https://www.geeksforgeeks.org/references-in-c/)

C 和 C++ 支持不同于大多数其他编程语言的指针。其他语言包括 C++、Java、Python、Ruby、Perl 和 PHP 都支持引用。

从表面上看，引用和指针非常相似，都用来让一个变量提供对另一个变量的访问。由于两者都提供了许多相同的功能，所以通常不清楚这些不同的机制之间有什么不同。在本文中，我将尝试说明指针和引用之间的区别。

[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/):指针是保存另一个变量内存地址的变量。指针需要用 ***** 运算符取消引用，才能访问它所指向的内存位置。

[References](https://www.geeksforgeeks.org/references-in-c/) :引用变量是别名，即已经存在的变量的另一个名称。像指针一样，引用也是通过存储对象的地址来实现的。
引用可以被认为是一个常量指针(不要和指向常量值的指针混淆！)具有自动间接性，即编译器将为您应用 ***** 运算符。

```cpp
int i = 3; 

// A pointer to variable i (or stores
// address of i)
int *ptr = &i; 

// A reference (or alias) for i.
int &ref = i; 
```

**差异**:

**1。初始化:**指针可以这样初始化:

```cpp
 int a = 10;        
  int *p = &a;    
         OR 
     int *p;
   p = &a;
we can declare and initialize pointer at same step or in multiple line.
```

2.而在参考文献中，

```cpp
int a=10;
int &p=a;  //it is correct
   but
int &p;
 p=a;    // it is incorrect as we should declare and initialize references at single step.
```

**3。注意:**这种差异可能因编译器而异。以上区别是关于 turbo IDE 的。

**4。重新分配:**指针可以重新分配。这个属性对于实现链表、树等数据结构非常有用。请参见以下示例:

```cpp
int a = 5;
int b = 6;
int *p;
p =  &a;
p = &b;
```

5.另一方面，引用不能重新分配，必须在初始化时分配。

```cpp
int a = 5;
int b = 6;
int &p = a;
int &p = b;  //At this line it will show error as "multiple declaration is not allowed".

However it is valid statement,
int &q=p;
```

**6。内存地址:**指针在堆栈上有自己的内存地址和大小，而引用共享相同的内存地址(与原始变量)，但也会占用堆栈上的一些空间。

```cpp
   int &p = a;
   cout << &p << endl << &a;
```

**7。空值:**指针可以直接赋空，而引用不能。与引用相关联的约束(不为空，不重新分配)确保底层操作不会遇到异常情况。

**8。间接性:**您可以拥有指向提供额外间接性级别的指针的指针。而引用只提供了一个间接层。即，

```cpp
In Pointers,
int a = 10;
int *p;
int **q;  //it is valid.
p = &a;
q = &p;

Whereas in references,

int &p = a;
int &&q = p; //it is reference to reference, so it is an error.
```

**9。算术运算:**可以对指针执行各种算术运算，而没有所谓的引用算术。(但是你可以获取一个引用所指向的对象的地址，并对其进行指针运算，就像在& obj + 5 中一样)。)

**什么时候用什么**

性能完全相同，因为引用在内部实现为指针。但是你仍然可以在头脑中保留一些要点来决定何时使用什么:

*   使用引用
    *   在函数参数和返回类型中。
*   使用指针:
    *   如果需要指针算术或传递空指针，请使用指针。例如，对于数组(请注意，数组访问是使用指针算法实现的)。
    *   要实现像链表、树等数据结构及其算法，因为要指向不同的单元格，我们必须使用指针的概念。

[引用自 C++ FAQ Lite](https://isocpp.org/wiki/faq/references#refs-vs-ptrs) :可以的时候用引用，必须的时候用指针。每当您不需要“重新拔插”时，引用通常比指针更受欢迎。这通常意味着引用在类的公共接口中最有用。引用通常出现在对象的表面，指针出现在内部。

上述情况的例外是函数的参数或返回值需要一个“哨兵”引用——一个不引用对象的引用。这通常最好通过返回/获取一个指针，并赋予空指针这一特殊意义来实现(引用必须总是别名对象，而不是取消引用的空指针)。

**相关文章:**
[我们什么时候传递参数作为参考或指针？](https://www.geeksforgeeks.org/when-do-we-pass-arguments-by-reference-or-pointer/)

本文由**里沙夫·拉吉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。