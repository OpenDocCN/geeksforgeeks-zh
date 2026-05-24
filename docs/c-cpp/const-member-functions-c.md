# c++ 中的 Const 成员函数

> 原文:[https://www.geeksforgeeks.org/const-member-functions-c/](https://www.geeksforgeeks.org/const-member-functions-c/)

像成员函数和成员函数参数一样，类的对象也可以声明为 **const** 。声明为 const 的对象不能被修改，因此只能调用 const 成员函数，因为这些函数确保不修改对象。
可以通过在对象声明前加上 const 关键字来创建 const 对象。任何更改 const 对象的数据成员的尝试都会导致编译时错误。
**语法:**

```cpp
const Class_Name Object_name; 
```

*   当一个函数被声明为常量时，它可以在任何类型的对象上被调用，常量对象和非常量对象。
*   每当一个对象被声明为 const 时，它需要在声明时被初始化。但是，声明时的对象初始化只有在构造函数的帮助下才有可能。

当函数的声明中使用了 const 关键字时，函数就变成了 const。const 函数的思想是不允许它们修改调用它们的对象。建议将尽可能多的函数设置为常量，以避免对对象的意外更改。
下面是一个简单的常量函数的例子。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

class Test {
    int value;

public:
    Test(int v = 0) { value = v; }

    int getValue() const { return value; }
};

int main()
{
    Test t(20);
    cout << t.getValue();
    return 0;
}
```

**输出:**

```cpp
20
```

当一个函数被声明为常量时，它可以在任何类型的对象上被调用。非常数函数只能由非常数对象调用。
例如，以下程序有编译器错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

class Test {
    int value;
public:
    Test(int v = 0) {value = v;}
    int getValue() {return value;}
};

int main() {
    const Test t;
    cout << t.getValue();
    return 0;
}
```

**输出:**

```cpp
 passing 'const Test' as 'this' argument of 'int 
Test::getValue()' discards qualifiers
```

让我们看另一个例子:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Demonstration of constant object,
// show that constant object can only
// call const member function
#include<iostream>
using namespace std;
class Demo
{
    int value;
    public:
    Demo(int v = 0) {value = v;}
    void showMessage()
    {
        cout<<"Hello World We are Tushar, "
        "Ramswarup, Nilesh and Subhash Inside"
        " showMessage() Function"<<endl;
    }
    void display()const
    {
        cout<<"Hello world I'm Rancho "
        "Baba Inside display() Function"<<endl;
    }
};
int main()
{
   //Constant object are initialised at the time of declaration using constructor
    const Demo d1;
    //d1.showMessage();Error occurred if uncomment.
    d1.display();
    return(0);
}
```

```cpp
OUTPUT : Hello world I'm Rancho Baba Inside display() Function
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。