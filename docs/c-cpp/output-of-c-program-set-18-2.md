# c++ 程序输出|第 18 集

> 原文:[https://www.geeksforgeeks.org/output-of-c-program-set-18-2/](https://www.geeksforgeeks.org/output-of-c-program-set-18-2/)

预测以下 C++ 程序的输出。

**问题 1**

```cpp
#include <iostream>
using namespace std;

template <int N>
class A {
   int arr[N];
public:
   virtual void fun() { cout << "A::fun()"; }
};

class B : public A<2> {
public:
   void fun() { cout << "B::fun()"; }
};

class C : public B { };

int main() {
   A<2> *a = new C;
   a->fun();
   return 0;
}
```

输出:

```cpp
B::fun()
```

一般来说，在 C++ 中使用模板的目的是为了避免代码冗余。我们创建的泛型类(或函数)可以用于任何数据类型，只要逻辑相同。数据类型成为一个参数，当数据类型被传递时，类/函数的实例在编译时被创建。C++ 模板也允许非类型(表示值的参数，而不是数据类型)的东西作为参数。
在上面的程序中，有一个泛型类 A，它取一个非类型参数 N，类 B 继承自泛型类 A 的一个实例，A 的这个实例的 N 值为 2。乙类超越了甲类< 2 >的乐趣()。C 类从 B 继承而来，在 main()中，有一个 A 类型的指针‘A’<2>指向 C 的一个实例，调用‘A->fun()’时，B 类的函数被执行，因为 fun()是虚函数，虚函数是根据实际对象调用的，而不是根据指针调用的。C 类中没有函数‘fun()’，所以在层次结构中查找，在 B.2 类> 2 >中找到

**问题 2**

```cpp
#include <iostream>
using namespace std;

template <int i>
int fun()
{
   i =20; 
}

int main() {
   fun<4>();
   return 0;
}
```

输出:

```cpp
 Compiler Error
```

非类型参数的值必须是常量，因为它们在编译时用于创建类/函数的实例。在上面的程序中，templated fun()接收一个非类型参数并试图修改它，这是不可能的。因此，编译器出错。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论