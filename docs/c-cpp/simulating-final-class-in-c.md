# 在 C++ 中模拟最终类

> 原文:[https://www.geeksforgeeks.org/simulating-final-class-in-c/](https://www.geeksforgeeks.org/simulating-final-class-in-c/)

有没有想过如何用 C++ 设计一个不能被继承的类。Java 和 C#编程语言内置了这个特性。你可以在 java 中使用 [final](https://www.geeksforgeeks.org/final-keyword-in-java/) 关键字，在 C# 中使用[来使一个类不可扩展。](https://www.geeksforgeeks.org/c-sharp-sealed-class/)

下面是一个机制，使用它我们可以在 C++ 中实现相同的行为。它利用私有构造函数、虚拟继承和友元类。

在下面的代码中，我们使 ***【最终】*** 类不可继承。当一个类 ***派生*** 试图继承它时，我们得到一个编译错误。
一个额外的类 ***MakeFinal*** (其默认构造函数是私有的)用于我们的目的。 ***Final*** 的构造函数可以将 ***MakeFinal*** 的私有构造函数调用为 ***Final*** 是 ***MakeFinal*** 的朋友。

> **注:** ***MakeFinal*** 也是虚拟基类。这样做的原因是通过*派生类*的构造函数调用 ***MakeFinal*** 的构造函数，而不是 *Final* (虚拟基类的构造函数不是由继承它的类调用，而是由具体类的构造函数调用)。

既然在 **C++ 11** 中有对**[**最终说明符**](https://www.geeksforgeeks.org/c-final-specifier/) 的支持，第三个例子展示了它的实现。**

## **C++**

```cpp
// C++ program with compilation
// error to demonstrate that
// Final class cannot be inherited
#include <iostream>
using namespace std;

// The class to be made final
class Final;

// used to make the Final class final
class MakeFinal {
private:
    MakeFinal() { cout << "MakFinal constructor" << endl; }
    friend class Final;
};

class Final : virtual MakeFinal {
public:
    Final() { cout << "Final constructor" << endl; }
};

// Compiler error
class Derived : public Final {
public:
    Derived() { cout << "Derived constructor" << endl; }
};

int main(int argc, char* argv[])
{
    Derived d;
    return 0;
}
```

****输出****

```cpp
 In constructor 'Derived::Derived()':
  error: 'MakeFinal::MakeFinal()' is private
```

**在上例中， ***派生*** **的**构造函数直接调用 ***MakeFinal 的*** 构造函数， ***MakeFinal*** 的构造函数是私有的，因此我们得到编译错误。**

**您可以创建****类的对象，因为它是***makefile***的朋友类，并且可以访问其构造函数。例如，以下程序运行良好。******

## ****C++****

```cpp
**// C++ program without any
// compilation error to demonstrate
// that instances of the Final
// class can be created

#include <iostream>
using namespace std;

class Final;

class MakeFinal {
private:
    MakeFinal() { cout << "MakeFinal constructor" << endl; }
    friend class Final;
};

class Final : virtual MakeFinal {
public:
    Final() { cout << "Final constructor" << endl; }
};

int main(int argc, char* argv[])
{
    Final f;
    return 0;
}**
```

******Output**

```cpp
MakeFinal constructor
Final constructor
```**** 

### ****C++ 11 更新:****

****在 C++ 11 中，我们可以通过使用 [**最终**](https://www.geeksforgeeks.org/c-final-specifier/) 说明符来使基类不可继承。例如，下面的代码给出了一个编译错误，因为基类被声明为 final。****

## ****C++****

```cpp
**// C++ Program with compilation error
// as the base class is declared as final

#include <iostream>
using namespace std;

class Base final {
    // body
};

// Compile error because base class is final
class Derived : public Base {
    // body
};

int main() {
  return 0;
}**
```

******输出******

```cpp
**prog.cpp:8:7: error: cannot derive from ‘final’ base ‘base’ in derived type ‘derive’
 class derive: public base  // compile error because base class is final**
```

****本文由 **Gopal Gorthi** 编辑，GeeksforGeeks 团队审核。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。****