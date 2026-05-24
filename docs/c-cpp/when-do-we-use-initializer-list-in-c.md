# 我们什么时候在 C++ 中使用初始化列表？

> 原文:[https://www . geesforgeks . org/when-do-we-use-initializer-list-in-c/](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)

初始化列表用于初始化类的数据成员。要初始化的成员列表由构造函数表示为逗号分隔列表，后跟冒号。下面是一个使用初始化列表初始化点类的 x 和 y 的例子。

## C++

```cpp
#include<iostream>
using namespace std;

class Point {
private:
    int x;
    int y;
public:
    Point(int i = 0, int j = 0):x(i), y(j) {}
    /*  The above use of Initializer list is optional as the
        constructor can also be written as:
        Point(int i = 0, int j = 0) {
            x = i;
            y = j;
        }
    */   

    int getX() const {return x;}
    int getY() const {return y;}
};

int main() {
  Point t1(10, 15);
  cout<<"x = "<<t1.getX()<<", ";
  cout<<"y = "<<t1.getY();
  return 0;
}

/* OUTPUT:
   x = 10, y = 15
*/
```

上面的代码只是初始化列表语法的一个例子。在上面的代码中，x 和 y 也可以很容易地在构造函数内部初始化。但是有些情况下，构造函数内部的数据成员初始化不起作用，必须使用初始化列表。以下是这样的情况:
**1)对于非静态常量数据成员的初始化:**
常量数据成员必须使用初始化列表进行初始化。在下面的例子中，“t”是测试类的常量数据成员，并使用初始化列表进行初始化。初始化初始化列表中 const 数据成员的原因是因为没有为 const 数据成员单独分配内存，它被折叠在符号表中，因此我们需要在初始化列表中初始化它。
此外，它是一个参数化的构造函数，我们不需要调用赋值运算符，这意味着我们避免了一个额外的操作。

## C++

```cpp
#include<iostream>
using namespace std;

class Test {
    const int t;
public:
    Test(int t):t(t) {}  //Initializer list must be used
    int getT() { return t; }
};

int main() {
    Test t1(10);
    cout<<t1.getT();
    return 0;
}

/* OUTPUT:
   10
*/
```

**2)对于引用成员的初始化:**
引用成员必须使用初始化列表初始化。在下面的例子中，“t”是 Test 类的引用成员，并使用 Initializer List 进行初始化。

## C++

```cpp
// Initialization of reference data members
#include<iostream>
using namespace std;

class Test {
    int &t;
public:
    Test(int &t):t(t) {}  //Initializer list must be used
    int getT() { return t; }
};

int main() {
    int x = 20;
    Test t1(x);
    cout<<t1.getT()<<endl;
    x = 30;
    cout<<t1.getT()<<endl;
    return 0;
}
/* OUTPUT:
    20
    30
 */
```

**3)对于没有默认构造函数的成员对象的初始化:**
在下面的例子中，类“A”的对象“A”是类“B”的数据成员，“A”没有默认构造函数。初始化列表必须用于初始化“a”。

## C++

```cpp
#include <iostream>
using namespace std;

class A {
    int i;
public:
    A(int );
};

A::A(int arg) {
    i = arg;
    cout << "A's Constructor called: Value of i: " << i << endl;
}

// Class B contains object of A
class B {
    A a;
public:
    B(int );
};

B::B(int x):a(x) {  //Initializer list must be used
    cout << "B's Constructor called";
}

int main() {
    B obj(10);
    return 0;
}
/* OUTPUT:
    A's Constructor called: Value of i: 10
    B's Constructor called
*/
```

如果类 A 既有默认构造函数又有参数化构造函数，那么如果我们想用默认构造函数初始化“A”，那么初始值设定项列表不是必须的，但是必须用参数化构造函数初始化“A”。
**4)对于基类成员的初始化:**和第 3 点一样，基类的参数化构造函数只能使用 Initializer List 调用。

## C++

```cpp
#include <iostream>
using namespace std;

class A {
    int i;
public:
    A(int );
};

A::A(int arg) {
    i = arg;
    cout << "A's Constructor called: Value of i: " << i << endl;
}

// Class B is derived from A
class B: A {
public:
    B(int );
};

B::B(int x):A(x) { //Initializer list must be used
    cout << "B's Constructor called";
}

int main() {
    B obj(10);
    return 0;
}
```

**5)当构造函数的参数名与数据成员**
相同时，如果构造函数的参数名与数据成员名相同，则必须使用[这个指针](http://msdn.microsoft.com/en-us/library/y0dddwwd.aspx)或初始化列表初始化数据成员。在下面的示例中，A()的成员名和参数名都是“I”。

## C++

```cpp
#include <iostream>
using namespace std;

class A {
    int i;
public:
    A(int );
    int getI() const { return i; }
};

A::A(int i):i(i) { }  // Either Initializer list or this pointer must be used
/* The above constructor can also be written as
A::A(int i) {
    this->i = i;
}
*/

int main() {
    A a(10);
    cout<<a.getI();
    return 0;
}
/* OUTPUT:
    10
*/
```

**6)出于性能原因:**
最好初始化初始化列表中的所有类变量，而不是在 body 内部赋值。考虑以下示例:

## C++

```cpp
// Without Initializer List
class MyClass {
    Type variable;
public:
    MyClass(Type a) {  // Assume that Type is an already
                     // declared class and it has appropriate
                     // constructors and operators
      variable = a;
    }
};
```

这里编译器按照以下步骤创建一个类型为 MyClass
1 的对象。首先为“a”调用类型的构造函数。
2。在 MyClass()构造函数的内部调用“Type”的赋值运算符进行赋值

```cpp
    variable = a;
```

3.最后“类型”的析构函数被称为“a”，因为它超出了范围。
现在考虑带有初始化列表
的 MyClass()构造函数的相同代码

## C++

```cpp
// With Initializer List
class MyClass {
    Type variable;
public:
    MyClass(Type a):variable(a) {   // Assume that Type is an already
                     // declared class and it has appropriate
                     // constructors and operators
    }
};
```

使用初始化列表，编译器遵循以下步骤:
1。“类型”类的参数化构造函数被调用来初始化:变量(a)。初始值设定项列表中的参数用于直接复制构造“变量”。
2。“类型”的析构函数被称为“a”，因为它超出了范围。
从这个例子可以看出，如果我们在构造函数体内使用赋值，有三个函数调用:构造函数+析构函数+一个加法赋值运算符调用。如果我们使用初始化列表，只有两个函数调用:复制构造函数+析构函数调用。参见[这篇](https://www.geeksforgeeks.org/output-of-c-program/)的帖子，了解关于这一点的运行示例。
在“真实”应用中，这种分配损失会更大，因为这种变量会很多。感谢 *ptr* 增加了这一点。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。