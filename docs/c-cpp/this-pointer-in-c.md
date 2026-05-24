# '这个'指针在 C++ 中

> 原文:[https://www.geeksforgeeks.org/this-pointer-in-c/](https://www.geeksforgeeks.org/this-pointer-in-c/)

为了理解“这个”指针，知道对象如何看待类的函数和数据成员是很重要的。

1.  每个对象都有自己的数据成员副本。
2.  all-访问与代码段中相同的函数定义。

这意味着每个对象都有自己的数据成员副本，所有对象共享一个成员函数副本。
那么现在的问题是，如果每个成员函数只有一个副本存在，并且被多个对象使用，那么如何访问和更新合适的数据成员呢？
编译器提供一个隐式指针和函数名作为“this”。
“this”指针作为隐藏参数传递给所有非静态成员函数调用，并可作为所有非静态函数体内的局部变量使用。“this”指针在静态成员函数中不可用，因为静态成员函数可以在没有任何对象(带有类名)的情况下调用。
对于类 X，这个指针的类型是‘X *’。另外，如果 X 的成员函数被声明为 const，那么这个指针的类型就是“const X * ”(参见[这个 GFact](https://www.geeksforgeeks.org/g-fact-77/) )

在早期的 C++ 版本中会让“this”指针被改变；通过这样做，程序员可以改变一个方法正在处理的对象。这个特性最终被移除了，现在这个在 C++ 中是一个 r 值。
C++ 通过调用以下代码让对象自我毁灭:

```cpp
delete this;
```

正如 Stroustrup 所说，“这”可以是引用而不是指针，但是在早期版本的 C++ 中，引用并不存在。如果将“this”实现为引用，则可以避免上述问题，并且它可能比指针更安全。

以下是使用“this”指针的情况:

**1)当局部变量名称与成员名称相同时**

```cpp
#include<iostream>
using namespace std;

/* local variable is same as a member's name */
class Test
{
private:
   int x;
public:
   void setX (int x)
   {
       // The 'this' pointer is used to retrieve the object's x
       // hidden by the local variable 'x'
       this->x = x;
   }
   void print() { cout << "x = " << x << endl; }
};

int main()
{
   Test obj;
   int x = 20;
   obj.setX(x);
   obj.print();
   return 0;
}
```

输出:

```cpp
 x = 20
```

对于构造函数，当参数名与成员名相同时，也可以使用[初始化列表](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)。

**2)返回对调用对象的引用**

```cpp
/* Reference to the calling object can be returned */ 
Test& Test::func ()
{
   // Some processing
   return *this;
} 
```

当返回对局部对象的引用时，返回的引用可用于对单个对象的**链函数调用**。

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
  int x;
  int y;
public:
  Test(int x = 0, int y = 0) { this->x = x; this->y = y; }
  Test &setX(int a) { x = a; return *this; }
  Test &setY(int b) { y = b; return *this; }
  void print() { cout << "x = " << x << " y = " << y << endl; }
};

int main()
{
  Test obj1(5, 5);

  // Chained function calls.  All calls modify the same object
  // as the same object is returned by reference
  obj1.setX(10).setY(20);

  obj1.print();
  return 0;
}
```

输出:

```cpp
x = 10 y = 20
```

**练习:**
预测以下程序的输出。如果存在编译错误，请修复它们。

**问题 1**

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
  int x;
public:
  Test(int x = 0) { this->x = x; }
  void change(Test *t) { this = t; }
  void print() { cout << "x = " << x << endl; }
};

int main()
{
  Test obj(5);
  Test *ptr = new Test (10);
  obj.change(ptr);
  obj.print();
  return 0;
}
```

**问题 2**

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
  int x;
  int y;
public:
  Test(int x = 0, int y = 0) { this->x = x; this->y = y; }
  static void fun1() { cout << "Inside fun1()"; }
  static void fun2() { cout << "Inside fun2()"; this->fun1(); }
};

int main()
{
  Test obj;
  obj.fun2();
  return 0;
}
```

**第三题**

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
  int x;
  int y;
public:
  Test (int x = 0, int y = 0) { this->x = x; this->y = y; }
  Test setX(int a) { x = a; return *this; }
  Test setY(int b) { y = b; return *this; }
  void print() { cout << "x = " << x << " y = " << y << endl; }
};

int main()
{
  Test obj1;
  obj1.setX(10).setY(20);
  obj1.print();
  return 0;
}
```

**问题 4**

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
  int x;
  int y;
public:
  Test(int x = 0, int y = 0) { this->x = x; this->y = y; }
  void setX(int a) { x = a; }
  void setY(int b) { y = b; }
  void destroy()  { delete this; }
  void print() { cout << "x = " << x << " y = " << y << endl; }
};

int main()
{
  Test obj;
  obj.destroy();
  obj.print();
  return 0;
}
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论