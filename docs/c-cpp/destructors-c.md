# c++ 中的析构函数

> 原文:[https://www.geeksforgeeks.org/destructors-c/](https://www.geeksforgeeks.org/destructors-c/)

**什么是析构函数？**
析构函数是一个实例成员函数，每当一个对象将要被销毁时，它就会被自动调用。也就是说，析构函数是对象被销毁之前最后一个被调用的函数。

这里需要注意的是，如果对象是使用 new 创建的，或者构造函数使用 new 来分配驻留在堆内存或空闲存储中的内存，析构函数应该使用 delete 来释放内存。

**语法:**

```cpp
~constructor-name();
```

**析构函数的属性:**

*   当对象被销毁时，析构函数被自动调用。
*   它不能声明为静态或常量。
*   析构函数没有参数。
*   它没有返回类型，甚至没有无效。
*   具有析构函数的类的对象不能成为联合的成员。
*   析构函数应该在类的公共部分声明。
*   程序员不能访问析构函数的地址。

**析构函数什么时候调用？**
当对象超出范围时自动调用析构函数:
(1)函数结束
(2)程序结束
(3)包含局部变量的块结束
(4)调用删除操作符

**析构函数和普通成员函数有什么不同？**
析构函数与前面带有波浪号(~)
的类同名，析构函数不接受任何参数，也不返回任何内容

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
class String {
private:
    char* s;
    int size;

public:
    String(char*); // constructor
    ~String(); // destructor
};

String::String(char* c)
{
    size = strlen(c);
    s = new char[size + 1];
    strcpy(s, c);
}
String::~String() { delete[] s; }
```

**一个类可以有多个析构函数吗？**
不，一个类中只能有一个析构函数，classname 前面加~，没有参数，没有返回类型。

**我们什么时候需要写一个用户定义的析构函数？**
如果我们没有在类中编写自己的析构函数，编译器会为我们创建一个默认的析构函数。默认析构函数工作正常，除非我们在类中动态分配了内存或指针。当一个类包含指向类中分配的内存的指针时，我们应该编写一个析构函数，在类实例被销毁之前释放内存。必须这样做才能避免内存泄漏。

**析构函数可以是虚拟的吗？**
是的，事实上，当我们有虚函数的时候，在基类中让析构函数虚化总是一个好主意。详见[虚拟析构器](https://www.geeksforgeeks.org/g-fact-37/)。
你可能想参加一个关于析构函数的[测验。](https://www.geeksforgeeks.org/c-plus-plus-gq/destructors-gq/)

**相关文章:**
[c++ 中的构造函数](https://www.geeksforgeeks.org/constructors-c/)
[虚拟析构函数](https://www.geeksforgeeks.org/virtual-destructor/)
[c++ 中的纯虚拟析构函数](https://www.geeksforgeeks.org/pure-virtual-destructor-c/)
如发现有不正确的地方请写评论，或者想分享以上讨论话题的更多信息。