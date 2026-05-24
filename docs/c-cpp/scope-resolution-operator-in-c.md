# c++ 中的范围解析运算符

> 原文:[https://www . geesforgeks . org/scope-resolution-operator-in-c/](https://www.geeksforgeeks.org/scope-resolution-operator-in-c/)

在 C++ 中，范围解析运算符是 **::** 。它用于以下目的。

**1)当存在同名局部变量时，访问全局变量:**

```cpp
// C++ program to show that we can access a global variable
// using scope resolution operator :: when there is a local 
// variable with same name 
#include<iostream> 
using namespace std;

int x;  // Global x

int main()
{
  int x = 10; // Local x
  cout << "Value of global x is " << ::x;
  cout << "\nValue of local x is " << x;  
  return 0;
}
```

输出:

```cpp
Value of global x is 0
Value of local x is 10

```

**2)定义类外的函数。**

```cpp
// C++ program to show that scope resolution operator :: is used
// to define a function outside a class
#include<iostream> 
using namespace std;

class A 
{
public: 

   // Only declaration
   void fun();
};

// Definition outside class using ::
void A::fun()
{
   cout << "fun() called";
}

int main()
{
   A a;
   a.fun();
   return 0;
}
```

输出:

```cpp
fun() called

```

**3)访问类的静态变量。**

```cpp
// C++ program to show that :: can be used to access static
// members when there is a local variable with same name
#include<iostream>
using namespace std;

class Test
{
    static int x;  
public:
    static int y;   

    // Local parameter 'a' hides class member
    // 'a', but we can access it using ::
    void func(int x)  
    { 
       // We can access class's static variable
       // even if there is a local variable
       cout << "Value of static x is " << Test::x;

       cout << "\nValue of local x is " << x;  
    }
};

// In C++, static members must be explicitly defined 
// like this
int Test::x = 1;
int Test::y = 2;

int main()
{
    Test obj;
    int x = 3 ;
    obj.func(x);

    cout << "\nTest::y = " << Test::y;

    return 0;
}
```

输出:

```cpp
Value of static x is 1
Value of local x is 3
Test::y = 2;

```

**4)在多重继承的情况下:**
如果两个祖先类中存在相同的变量名，我们可以使用范围解析运算符来区分。

```cpp
// Use of scope resolution operator in multiple inheritance.
#include<iostream>
using namespace std;

class A
{
protected:
    int x;
public:
    A() { x = 10; }
};

class B
{
protected:
    int x;
public:
    B() { x = 20; }
};

class C: public A, public B
{
public:
   void fun()
   {
      cout << "A's x is " << A::x;
      cout << "\nB's x is " << B::x;
   }
};

int main()
{
    C c;
    c.fun();
    return 0;
}
```

输出:

```cpp
A's x is 10
B's x is 20
```

**5)对于命名空间**
如果两个命名空间中存在同名的类，我们可以使用带有范围解析操作符的命名空间名称来引用该类，而不会有任何冲突

```cpp
// Use of scope resolution operator for namespace.
#include<iostream>

int main(){
    std::cout << "Hello" << std::endl;

}
```

```cpp
Here, cout and endl belong to the std namespace.

```

**6)引用另一个类中的一个类:**
如果一个类存在于另一个类中，我们可以使用嵌套类来引用使用范围解析操作符的嵌套类

```cpp
// Use of scope resolution class inside another class.
#include<iostream>
using namespace std;

class outside
{
public:
      int x;
      class inside
      {
      public:
            int x;
            static int y; 
            int foo();

      };
};
int outside::inside::y = 5; 

int main(){
    outside A;
    outside::inside B;

}
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论