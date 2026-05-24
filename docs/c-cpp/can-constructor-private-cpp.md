# c++ 中构造函数可以是私有的吗？

> 原文:[https://www.geeksforgeeks.org/can-constructor-private-cpp/](https://www.geeksforgeeks.org/can-constructor-private-cpp/)

**先决条件:** [构造函数](https://www.geeksforgeeks.org/constructors-c/)
A **构造函数**是初始化类的对象的类的特殊成员函数。在 C++ 中，当创建类的对象时，会自动调用构造函数。

默认情况下，构造函数在类的公共部分定义。那么，问题是构造函数可以在类的私有部分定义吗？
**回答:可以，构造函数可以在类**的私有部分定义

**如何在私有部分使用构造函数？**

1.  **Using Friend Class :** If we want that class should not be instantiated by anyone else but only by a friend class.

    ```cpp
    // CPP program to demonstrate usage of 
    // private constructor
    #include <iostream>
    using namespace std;

    // class A
    class A{
    private:
        A(){
           cout << "constructor of A\n";
        }
        friend class B;
    };

    // class B, friend of class A
    class B{
    public:
        B(){
            A a1;
            cout << "constructor of B\n";
        }
    };

    // Driver program
    int main(){
        B b1;
        return 0;
    }
    ```

    输出:

    ```cpp
    constructor of A
    constructor of B

    ```

    如果评论行**好友 B 类**，会遇到以下错误:

    ```cpp
    test1.cpp: In constructor ‘B::B()’:
    test1.cpp:9:5: error: ‘A::A()’ is private
         A(){
         ^
    test1.cpp:19:11: error: within this context
             A a1;

    ```

2.  **使用 Singleton 设计模式:**当我们想要设计一个 [singleton](https://www.geeksforgeeks.org/singleton-design-pattern/) 类的时候。这意味着系统不是创建几个类对象，而是由单个对象或数量非常有限的对象驱动。
3.  **Named Constructor Idiom :** Since constructor has same name as of class, different constructors are differentiated by their parameter list, but if numbers of constructors is more, then implementation can become error prone.

    使用命名构造函数习惯用法，您可以在私有或受保护的部分声明类的所有构造函数，然后为了访问类的对象，您可以创建公共静态函数。

    例如，考虑下面的 CPP 程序

    ```cpp
    // CPP program to demonstrate
    // ambiguous nature of constructor
    // with same no of parameters of same type
    #include <iostream>
    using namespace std;
    class Point 
    {
        public:

        // Rectangular coordinates
        Point(float x, float y);     

        // Polar coordinates (radius and angle)
        Point(float r, float a);     

        // error: ‘Point::Point(float, float)’ cannot
        // be overloaded
    };
    int main()
    {
        // Ambiguous: Which constructor to be called ?
        Point p = Point(5.7, 1.2); 
        return 0;
    }
    ```

    这个问题可以通过命名构造函数来解决。上述 CPP 计划可以改进如下:

    ```cpp
    // CPP program to demonstrate
    // named constructor idiom
    #include <iostream>
    #include <cmath>
    using namespace std;
    class Point 
    {
        private:
        float x1, y1;
        Point(float x, float y)
        {
            x1 = x;
            y1 = y;
        };
    public:
        // polar(radius, angle)
        static Point Polar(float, float); 

        // rectangular(x, y)
        static Point Rectangular(float, float); 
        void display();
    };

    // utility function for displaying of coordinates
    void Point :: display()
    {
        cout << "x :: " << this->x1 <<endl;
        cout << "y :: " << this->y1 <<endl;
    }

    // return polar coordinates
    Point Point :: Polar(float x, float y)
    {
        return Point(x*cos(y), x*sin(y));
    }

    // return rectangular coordinates
    Point Point :: Rectangular(float x, float y)
    {
        return Point(x,y);
    }
    int main()
    {
        // Polar coordinates
        Point pp = Point::Polar(5.7, 1.2);
        cout << "polar coordinates \n";
        pp.display();

        // rectangular coordinates
        Point pr = Point::Rectangular(5.7,1.2);
        cout << "rectangular coordinates \n";
        pr.display();
        return 0;
    }
    ```

    输出:

    ```cpp
    polar coordinates 
    x :: 2.06544
    y :: 5.31262
    rectangular coordinates 
    x :: 5.7
    y :: 1.2

    ```

**参考:**
1) [命名构造函数成语](https://isocpp.org/wiki/faq/ctors#named-ctor-idiom)T5】2)[一个构造函数在 cpp](https://stackoverflow.com/questions/18132590/can-a-constructor-be-private-in-c) 中可以是私有的吗

本文由 **[曼德普·辛格](https://github.com/msdeep14)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。