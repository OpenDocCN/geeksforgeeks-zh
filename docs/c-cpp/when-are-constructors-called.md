# 什么时候调用构造函数？

> 原文:[https://www.geeksforgeeks.org/when-are-constructors-called/](https://www.geeksforgeeks.org/when-are-constructors-called/)

什么时候为不同类型的对象调用构造函数，如全局、局部、静态局部、动态？
**1)全局对象:**对于全局对象，在调用 main()之前先调用构造函数。例如，见以下程序和输出:

## C

```cpp
#include<iostream>
using namespace std;

class Test
{
public:
  Test();
};

Test::Test()  {
    cout << "Constructor Called \n";
}

Test t1;

int main() {
    cout << "main() started\n";
    return 0;
}
/* OUTPUT:
      Constructor Called
      main() started
*/
```

**2)函数或块作用域(自动变量和常量)**对于非静态局部对象，当执行到达声明对象的点时，调用构造函数。例如，见以下程序和输出:

## C

```cpp
using namespace std;

class Test
{
public:
  Test();
};

Test::Test()  {
    cout << "Constructor Called \n";
}

void fun() {
  Test t1;
}

int main() {
    cout << "Before fun() called\n";
    fun();
    cout << "After fun() called\n";
    return 0;
}
/* OUTPUT:
       Before fun() called
       Constructor Called
       After fun() called
*/
```

对于局部静态对象来说，**第一次**执行的时间(也只有第一次)到达对象被声明的点。例如，以下程序的输出为:

## C

```cpp
#include<iostream>
using namespace std;

class Test
{
public:
  Test();
};

Test::Test()  {
    cout << "Constructor Called \n";
}

void fun() {
  static Test t1;
}

int main() {
    cout << "Before fun() called\n";
    fun();
    cout << "After fun() called\n";
    fun();  //constructor is not called this time.
    return 0;
}
/* OUTPUT
       Before fun() called
       Constructor Called
       After fun() called
*/
```

**3)类作用域:**创建对象时，编译器会确保调用其所有子对象(其成员和继承对象)的构造函数。如果成员有默认的构造函数或者没有参数的构造函数，那么这些构造函数会被自动调用，否则参数化的构造函数可以使用[初始化列表](http://www.cprogramming.com/tutorial/initialization-lists-c++.html)来调用。例如，参见程序 1 和程序 2 及其输出。

## C

```cpp
// PROGRAM 1: Constructor without any parameter
#include<iostream>
using namespace std;

class A
{
public:
  A();
};

A::A() {
    cout << "A's Constructor Called \n";
}

class B
{
  A t1;
public:
  B();
};

B::B() {
    cout << "B's Constructor Called \n";
}

int main() {
    B b;
    return 0;
}
/* OUTPUT:
      A's Constructor Called
      B's Constructor Called
*/
```

## C

```cpp
// PROGRAM 2: Constructor with parameter (using initializer list)
#include <iostream>
using namespace std;

class A
{
public:
    int i;
    A(int );
};

A::A(int arg)
{
    i = arg;
    cout << "A's Constructor called: Value of i: " << i << endl;
}

// Class B contains object of A
class B
{
    A a;
public:
    B(int );
};

B::B(int x):a(x)
{
    cout << "B's Constructor called";
}

int main()
{
    B obj(10);
    return 0;
}
/* OUTPUT
       A's Constructor called: Value of i: 10
       B's Constructor called
*/
```

**4)动态对象:**对于动态分配的对象，构造函数由新的运算符调用。例如，参见以下程序和输出。

## C

```cpp
#include<iostream>

using namespace std;

class Test
{
public:
  Test();
};

Test::Test()  {
    cout << "Constructor Called \n";
}

int main()
{
    cout << "Before new called\n";
    Test *t1 = new Test;
    cout << "After new called\n";
    return 0;
}
/* OUTPUT
      Before new called
      Constructor Called
      After new called
*/
```

**参考文献:**
[http://web . cs . wpi . edu/~ cs 2303/C10/Protected/听课-C10/Week5 _ more classes . PPT](http://web.cs.wpi.edu/~cs2303/c10/Protected/Lectures-C10/Week5_MoreClasses.ppt)
如发现有不正确的地方，或想分享以上讨论话题的更多信息，请写评论。