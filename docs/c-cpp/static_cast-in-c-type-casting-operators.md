# c++ 中的 static _ cast | Type Casting 运算符

> 原文:[https://www . geesforgeks . org/static _ cast-in-c-type-casting-operators/](https://www.geeksforgeeks.org/static_cast-in-c-type-casting-operators/)

强制转换运算符是一元运算符**，它强制将一种数据类型转换为另一种数据类型。
C++ 支持四种类型的铸造:**

> **1.静投
> 2。动态铸造
> 3。 [Const Cast](https://www.geeksforgeeks.org/casting-operators-in-c-set-1-const_cast/)
> 4。[重新诠释铸造](https://www.geeksforgeeks.org/reinterpret_cast-in-cpp/)**

****静态施法:**这是可以使用的最简单的施法类型。这是一个**编译时剧组**。它可以进行类型间的隐式转换(比如 int 到 float，或者指针到 void*)，还可以调用显式转换函数(或者隐式转换函数)。
**例如****

```cpp
#include <iostream>
using namespace std;
int main()
{
    float f = 3.5;
    int a = f; // this is how you do in C
    int b = static_cast<int>(f);
    cout << b;
}
```

****输出:****

```cpp
3
```

**现在让我们对代码做一些修改。**

```cpp
#include <iostream>
using namespace std;
int main()
{
    int a = 10;
    char c = 'a';

    // pass at compile time, may fail at run time
    int* q = (int*)&c; 
    int* p = static_cast<int*>(&c);
    return 0;
}
```

**如果您编译代码，您将会得到一个错误:**

```cpp
[Error] invalid static_cast from type 'char*' to type 'int*'
```

**这意味着，即使你认为你可以将一个特定的对象类型转换成另一个，但是它的**是非法的**，static_cast 也不会允许你这样做。**

**让我们再举一个在类之间转换对象的例子。**

```cpp
#include <iostream>
#include <string>
using namespace std;
class Int {
    int x;

public:
    Int(int x_in = 0)
        : x{ x_in }
    {
        cout << "Conversion Ctor called" << endl;
    }
    operator string()
    {
        cout << "Conversion Operator" << endl;
        return to_string(x);
    }
};
int main()
{
    Int obj(3);
    string str = obj;
    obj = 20;
    string str2 = static_cast<string>(obj);
    obj = static_cast<Int>(30);
    return 0;
}
```

**运行上面的代码:**

```cpp
Conversion Ctor called
Conversion Operator
Conversion Ctor called
Conversion Operator
Conversion Ctor called
```

**让我们试着理解上面的输出:**

1.  **当**对象**被创建时，那么构造函数被调用，在我们的例子中它也是一个转换构造函数(对于 C++ 来说，14 个规则是位改变的)。**
2.  **当您从**对象**中创建**字符串**时，编译器不会抛出错误，因为我们已经定义了转换运算符。**
3.  **当你做`obj=20`的时候，实际上是在调用转换构造函数。**
4.  **当你用**静态 _cast** 制作 **str2** 时，和`string str=obj;`很相似，但是类型检查很严格。**
5.  **当你写`obj=static_cast<Int>(30)`的时候，你是用 static_cast 把 30 转换成 **Int** 。**

**让我们举一个涉及继承的例子。**

```cpp
#include <iostream>
using namespace std;
class Base {
};
class Derived : public Base {
};
int main()
{
    Derived d1;
    Base* b1 = (Base*)(&d1); // allowed
    Base* b2 = static_cast<Base*>(&d1);

    return 0;
}
```

**上面的代码将编译没有任何错误。**

1.  **我们获取了`d1`的地址，并将其明确地铸造到`Base`中，并将其存储在`b1`中。**
2.  **我们取了`d1`的地址，用 static_cast 将其铸入`Base`并存储在`b2`中。**

**我们知道 static_cast 执行严格的类型检查，让我们稍微修改一下代码来看看它:**

```cpp
#include <iostream>
using namespace std;
class Base {
};
class Derived : private Base { // Inherited private/protected not public
};
int main()
{
    Derived d1;
    Base* b1 = (Base*)(&d1); // allowed
    Base* b2 = static_cast<Base*>(&d1);
    return 0;
}
```

**试着编译一下上面的代码，你看到了什么？？*编译错误！！！！！！！***

```cpp
[Error] 'Base' is an inaccessible base of 'Derived'
```

**以上代码即使继承为**保护的**，也不会**编译**。所以要使用 static_cast，将其作为公共继承。**

**使用 static_cast 将“往返”转换为 void 指针。**

```cpp
#include <iostream>
int main()
{
    int i = 10;
    void* v = static_cast<void*>(&i);
    int* ip = static_cast<int*>(v);
    return 0;
}
```