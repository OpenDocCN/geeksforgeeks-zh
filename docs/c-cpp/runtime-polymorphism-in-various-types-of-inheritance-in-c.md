# c++ 中各种类型继承的运行时多态性

> 原文:[https://www . geeksforgeeks . org/runtime-多态-各种类型的继承-in-c/](https://www.geeksforgeeks.org/runtime-polymorphism-in-various-types-of-inheritance-in-c/)

[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 允许用户对任何[类型的继承](https://www.geeksforgeeks.org/inheritance-in-c/)使用[虚拟函数](https://www.geeksforgeeks.org/virtual-function-cpp/)来使用[运行时多态](https://www.geeksforgeeks.org/polymorphism-in-c/)的概念。

下面是如何在所有类型的继承中实现运行时多态性:

1.  **【 Single inheritance:**

    ```cpp
    // C++ program to demonstrate Run Time
    // Polymorphism in Single Inheritance

    #include <iostream>
    using namespace std;

    // Base Class
    class Base {

    public:
        // Virtual function
        virtual void funct1()
        {
            cout << "Base::funct1() is called\n";
        }

        // Virtual function
        virtual void funct2(int x)
        {
            cout << "Base's Val of x:"
                 << x << endl;
        }

        // Non-Virtual Function
        void funct3()
        {
            cout << "Base is the Parent class!"
                 << endl;
        }
    };

    // Derived Class or Sub Class
    class Derived : public Base {
    private:
        // Virtual Functions
        // can also be Private!
        void funct1()
        {
            cout << "Derived::funct1() is called\n";
        }
        void funct2(int x)
        {
            cout << "Derived Class's Val of x:"
                 << x << endl;
        }
        void funct3()
        {
            cout << "It's the Derived class's"
                 << " funct3() called!" << endl;
        }
    };

    int main()
    {

        // Run-Time Polymorphism
        // in Single Inheritance
        Base* bptr = new Derived();

        // virtual function
        bptr->funct1();

        // virtual function
        bptr->funct2(12);

        // Non-virtual function
        bptr->funct3();

        return 0;
    }
    ```

    **Output:**

    ```cpp
    Derived::funct1() is called
    Derived Class's Val of x:12
    Base is the Parent class!

    ```

2.  **Multiple inheritance:**

    ```cpp
    #include <iostream>
    using namespace std;

    // Parent to Derived class
    class Base1 {
    public:
        // Non-Virtual function
        void funct1()
        {
            cout << "Base1::funct1() is called\n";
        }

        // Virtual function
        virtual void funct2(int x)
        {
            cout << "Base1's Val of x:"
                 << x << endl;
        }

        // Non-Virtual Function
        void funct3()
        {
            cout << "Base1 is the Parent class!"
                 << endl;
        }
    };

    // Second Parent to Derived class
    class Base2 {
    public:
        void funct1()
        {
            cout << "Base2::funct1() is called\n";
        }
        void funct2(int x)
        {
            cout << "Base2's Val of x:" << x << endl;
        }

        // Only Virtual Function
        // in Base2 Parent class
        virtual void funct3()
        {
            cout << "Base2 is Also a Parent class!"
                 << endl;
        }
    };

    // Derived Class of Base1 and Base2
    class Derived : public Base1, public Base2 {
    private:
        void funct1()
        {
            cout << "Derived::funct1() is called\n";
        }
        void funct2(int x)
        {
            cout << "Derived Class's Val of x:"
                 << x << endl;
        }
        void funct3()
        {
            cout << "Derived::funct3() is called "
                 << "and not Base2::funct3() due"
                 << " to RTP" << endl;
        }
    };

    int main()
    {
        Derived d;

        // Run-Time Polymorphism
        // in Multiple Inheritance
        Base1* b1ptr = &d;

        // Compile-Time Binding,
        // Hence Base1::funct1() will be called!
        b1ptr->funct1();

        // virtual function of Base1
        // RunTime PolyMorphism
        b1ptr->funct2(10);

        // Now Parent Class Base2
        // is also pointed to object 'd'
        // of Derived (to demonstrate RTP)
        Base2* b2ptr = &d;

        // virtual function of Base2
        // RunTime PolyMorphism
        b2ptr->funct3();

        return 0;
    }
    ```

    **Output:**

```cpp
Base1::funct1() is called
Derived Class's Val of x:10
Derived::funct3() is called and not Base2::funct3() due to RTP

```