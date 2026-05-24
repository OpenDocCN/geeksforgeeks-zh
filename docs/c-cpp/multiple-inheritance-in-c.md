# c++ 中的多重遗传

> 原文:[https://www.geeksforgeeks.org/multiple-inheritance-in-c/](https://www.geeksforgeeks.org/multiple-inheritance-in-c/)

多重继承是 C++ 的一个特性，其中一个类可以从多个类继承。

继承类的构造函数的调用顺序与它们被继承的顺序相同。例如，在下面的程序中，在 A 的构造函数之前调用 B 的构造函数。

```cpp
#include<iostream>
using namespace std;

class A
{
public:
  A()  { cout << "A's constructor called" << endl; }
};

class B
{
public:
  B()  { cout << "B's constructor called" << endl; }
};

class C: public B, public A  // Note the order
{
public:
  C()  { cout << "C's constructor called" << endl; }
};

int main()
{
    C c;
    return 0;
}
```

输出:

```cpp
B's constructor called
A's constructor called
C's constructor called
```

析构函数的调用顺序与构造函数相反。

**钻石问题**
当一个类的两个超类拥有共同的基类时，就会出现钻石问题。例如，在下图中，TA 类获得了 Person 类所有属性的两个副本，这导致了歧义。

![](img/c8b291a0dee767562c467866641323ee.png)

例如，考虑以下程序。

```cpp
#include<iostream>
using namespace std;
class Person {
   // Data members of person 
public:
    Person(int x)  { cout << "Person::Person(int ) called" << endl;   }
};

class Faculty : public Person {
   // data members of Faculty
public:
    Faculty(int x):Person(x)   {
       cout<<"Faculty::Faculty(int ) called"<< endl;
    }
};

class Student : public Person {
   // data members of Student
public:
    Student(int x):Person(x) {
        cout<<"Student::Student(int ) called"<< endl;
    }
};

class TA : public Faculty, public Student  {
public:
    TA(int x):Student(x), Faculty(x)   {
        cout<<"TA::TA(int ) called"<< endl;
    }
};

int main()  {
    TA ta1(30);
}
```

```cpp
Person::Person(int ) called
Faculty::Faculty(int ) called
Person::Person(int ) called
Student::Student(int ) called
TA::TA(int ) called
```

在上面的程序中，两次调用了‘Person’的构造函数。“人”的析构函数在对象“ta1”被析构时也会被调用两次。所以对象“ta1”有“人”的所有成员的两个副本，这导致歧义。*这个问题的解决方案是‘虚拟’关键词*。我们将“教师”和“学生”作为虚拟基类，以避免在“助教”课上出现两个“人”的副本。例如，考虑以下程序。

```cpp
#include<iostream>
using namespace std;
class Person {
public:
    Person(int x)  { cout << "Person::Person(int ) called" << endl;   }
    Person()     { cout << "Person::Person() called" << endl;   }
};

class Faculty : virtual public Person {
public:
    Faculty(int x):Person(x)   {
       cout<<"Faculty::Faculty(int ) called"<< endl;
    }
};

class Student : virtual public Person {
public:
    Student(int x):Person(x) {
        cout<<"Student::Student(int ) called"<< endl;
    }
};

class TA : public Faculty, public Student  {
public:
    TA(int x):Student(x), Faculty(x)   {
        cout<<"TA::TA(int ) called"<< endl;
    }
};

int main()  {
    TA ta1(30);
}
```

输出:

```cpp
Person::Person() called
Faculty::Faculty(int ) called
Student::Student(int ) called
TA::TA(int ) called
```

在上面的程序中，一次调用了‘Person’的构造函数。在上面的输出中需要注意的一点是，*Person 的默认构造函数叫做*。当我们使用' virtual '关键字时，即使父类显式调用参数化构造函数，默认情况下也会调用祖父类的默认构造函数。

**如何调用‘Person’类的参数化构造函数？**构造函数必须在‘TA’类中调用。例如，请参见以下程序。

```cpp
#include<iostream>
using namespace std;
class Person {
public:
    Person(int x)  { cout << "Person::Person(int ) called" << endl;   }
    Person()     { cout << "Person::Person() called" << endl;   }
};

class Faculty : virtual public Person {
public:
    Faculty(int x):Person(x)   {
       cout<<"Faculty::Faculty(int ) called"<< endl;
    }
};

class Student : virtual public Person {
public:
    Student(int x):Person(x) {
        cout<<"Student::Student(int ) called"<< endl;
    }
};

class TA : public Faculty, public Student  {
public:
    TA(int x):Student(x), Faculty(x), Person(x)   {
        cout<<"TA::TA(int ) called"<< endl;
    }
};

int main()  {
    TA ta1(30);
}
```

输出:

```cpp
Person::Person(int ) called
Faculty::Faculty(int ) called
Student::Student(int ) called
TA::TA(int ) called
```

一般不允许直接调用祖父母的构造函数，必须通过父类调用。仅当使用“virtual”关键字时才允许。

作为练习，预测以下程序的输出。

**问题 1**

```cpp
#include<iostream>
using namespace std;

class A
{
  int x;
public:
  void setX(int i) {x = i;}
  void print() { cout << x; }
};

class B:  public A
{
public:
  B()  { setX(10); }
};

class C:  public A  
{
public:
  C()  { setX(20); }
};

class D: public B, public C {
};

int main()
{
    D d;
    d.print();
    return 0;
}
```

**问题 2**

```cpp
#include<iostream>
using namespace std;

class A
{
  int x;
public:
  A(int i) { x = i; }
  void print() { cout << x; }
};

class B: virtual public A
{
public:
  B():A(10) {  }
};

class C:  virtual public A 
{
public:
  C():A(10) {  }
};

class D: public B, public C {
};

int main()
{
    D d;
    d.print();
    return 0;
}
```

发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息