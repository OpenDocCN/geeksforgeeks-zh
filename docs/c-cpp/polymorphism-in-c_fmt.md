# C++ 中的多态性

> 原文: [https://www.geeksforgeeks.org/polymorphism-in-c/](https://www.geeksforgeeks.org/polymorphism-in-c/)

多态这个词意味着有许多形式。简单地说，我们可以将多态性定义为一条消息以多种形式显示的能力。多态性的一个现实例子，一个人同时可以有不同的特征。喜欢一个男人的同时是一个父亲，一个丈夫，一个员工。所以同一个人在不同的情况下有不同的行为。这叫做多态性。多态性被认为是面向对象编程的重要特征之一。

## 在 C++ 中多态性主要分为两种类型

*   编译时多态性
*   运行时多态性

![Polymorphism-in-CPP](img/3dc67d709a4ea1de67d431708c48cd73.png)

### 编译时多态性

这种类型的多态性是通过函数重载或运算符重载实现的。

#### 函数重载

[Function Overloading](https://www.geeksforgeeks.org/function-overloading-c/)：当有多个函数名称相同但参数不同时，这些函数被称为**重载**。函数可以通过**改变参数数量**或/和**改变参数类型**来重载。
[函数重载的规则](https://www.geeksforgeeks.org/function-overloading-in-c/)

```cpp
// C++ program for function overloading
#include <bits/stdc++.h>
using namespace std;

class Geeks
{
    public:
    // function with 1 int parameter
    void func(int x)
    {
        cout << "value of x is " << x << endl;
    }

    // function with same name but 1 double parameter
    void func(double x)
    {
        cout << "value of x is " << x << endl;
    }

    // function with same name and 2 int parameters
    void func(int x, int y)
    {
        cout << "value of x and y is " << x << ", " << y << endl;
    }
};

int main() {
    Geeks obj1;

    // Which function is called will depend on the parameters passed
    // The first 'func' is called
    obj1.func(7);

    // The second 'func' is called
    obj1.func(9.132);

    // The third 'func' is called
    obj1.func(85,64);
    return 0;
}
```

**输出:**

```cpp
value of x is 7
value of x is 9.132
value of x and y is 85, 64
```

在上面的例子中，一个名为`func`的函数在三种不同的情况下有不同的行为，这就是多态的特性。

#### 运算符重载

[Operator Overloading](https://www.geeksforgeeks.org/operator-overloading-c/)：C++ 也提供重载运算符的选项。例如，我们可以使字符串类的运算符（`+`）来连接两个字符串。我们知道这是加法运算符，其任务是添加两个操作数。所以单个运算符`+`当放置在整数操作数之间时，将它们相加，当放置在字符串操作数之间时，将它们连接起来。

**示例**:

```cpp
// CPP program to illustrate
// Operator Overloading
#include<iostream>
using namespace std;

class Complex {
    private:
        int real, imag;
    public:
        Complex(int r = 0, int i =0)  {real = r;   imag = i;}

    // This is automatically called when '+' is used with
    // between two Complex objects
    Complex operator + (Complex const &obj) {
         Complex res;
         res.real = real + obj.real;
         res.imag = imag + obj.imag;
         return res;
    }
    void print() { cout << real << " + i" << imag << endl; }
};

int main()
{
    Complex c1(10, 5), c2(2, 4);
    Complex c3 = c1 + c2; // An example call to "operator+"
    c3.print();
}
```

输出:

```cpp
12 + i9
```

在上面的例子中，运算符`+`是重载的。运算符`+`是加法运算符，可以将两个数字(整数或浮点)相加，但在这里，运算符用于执行两个虚数或复数的相加。要详细了解操作员过载，请访问[这个](https://www.geeksforgeeks.org/operator-overloading-c/)链接。

### 运行时多态性

[Runtime polymorphism](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/)：这种类型的多态性是通过函数重写实现的。

#### 函数重写

[Function overriding](https://www.geeksforgeeks.org/override-keyword-c/) 则发生在派生类为基类的某个成员函数提供了定义时。该基类函数被称为**被重写**。

```cpp
// C++ program for function overriding
#include <bits/stdc++.h>
using namespace std;

class base
{
    public:
        virtual void print ()
        { cout<< "print base class" <<endl; }

        void show ()
        { cout<< "show base class" <<endl; }
};

class derived:public base
{
    public:
        void print () //print () is already virtual function in derived class, we could also declared as virtual void print () explicitly
        { cout<< "print derived class" <<endl; }

        void show ()
        { cout<< "show derived class" <<endl; }
};

//main function
int main()
{
    base *bptr;
    derived d;
    bptr = &d;

    //virtual function, binded at runtime (Runtime polymorphism)
    bptr->print();

    // Non-virtual function, binded at compile time
    bptr->show();

    return 0;
}
```

输出:

```cpp
print derived class
show base class
```

要详细了解运行时多态性，请访问[这个](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/)链接。

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。