# c++ 程序输出|第 14 集

> 原文:[https://www.geeksforgeeks.org/output-of-c-program-set-14/](https://www.geeksforgeeks.org/output-of-c-program-set-14/)

预测后续 C++ 程序的输出。

难度等级:菜鸟

**问题 1**

```cpp
#include <iostream>
using namespace std;

class A
{
    int id;
public:
    A (int i) { id = i; }
    void print () { cout << id << endl; }
};

int main()
{
    A a[2];
    a[0].print();
    a[1].print();
    return 0;
}
```

行“A a[2]”中有一个编译错误。a 类中没有默认构造函数，当我们自己编写参数化构造函数或复制构造函数时，编译器不会创建默认构造函数(参见本 Gfact[)。我们可以通过在类 A 中创建一个默认构造函数，或者使用下面的语法使用参数化构造函数初始化数组成员来修复这个错误。](https://www.geeksforgeeks.org/does-c-compiler-create-default-constructor-when-we-write-our-own/)

```cpp
 // Initialize a[0] with value 10 and a[1] with 20 
 A a[2] = { A(10),  A(20) } 
```

**问题 2**

```cpp
#include <iostream>
using namespace std;

class A
{
    int id;
    static int count;
public:
    A()
    {
        count++ ;
        id = count;
        cout << "constructor called " << id << endl;
    }
    ~A()
    {
        cout << "destructor called " << id << endl;
    }
};

int A::count = 0;

int main()
{
    A a[2];
    return 0;
}
```

输出:

```cpp
constructor called 1
constructor called 2
destructor called 2
destructor called 1

```

在上述程序中，首先创建对象 a[0]，但首先销毁对象 a[1]。对象总是按照与创建相反的顺序被销毁。颠倒顺序的原因是，以后创建的对象可能会使用以前创建的对象。例如，考虑下面的代码片段。

```cpp
A a;
B b(a);
```

在上面的代码中，对象“b”(在“a”之后创建)可能会在内部使用“a”的一些成员。所以在“b”之前破坏“a”可能会产生问题。因此，对象“b”必须在“a”之前销毁。

**第三题**

```cpp
#include <iostream>
using namespace std;

class A
{
   int aid;
public:
   A(int x)
   { aid = x; }
   void print()
   { cout << "A::aid = " <<aid; }
};

class B
{
    int bid;
public:
    static A a;
    B (int i) { bid = i; }
};

int main()
{
  B b(10);
  b.a.print();
  return 0;
}
```

编译器错误:对“B::a”
的未定义引用。类 B 有一个静态成员“a”。由于成员“a”是静态的，因此必须在类外部定义。类 A 没有默认构造函数，所以我们也必须在定义中传递一个值。增加一行“A B::A(10)；”会让这个项目成功。

以下程序运行良好，输出为“A::aid = 10”

```cpp
#include <iostream>
using namespace std;

class A
{
   int aid;
public:
   A(int x)
   { aid = x; }
   void print()
   { cout << "A::aid = " <<aid; }
};

class B
{
    int bid;
public:
    static A a;
    B (int i) { bid = i; }
};

A B::a(10);

int main()
{
  B b(10);
  b.a.print();
  return 0;
}
```

发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息