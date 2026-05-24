# c++ 中的匿名类

> 原文:[https://www.geeksforgeeks.org/anonymous-classes-in-cpp/](https://www.geeksforgeeks.org/anonymous-classes-in-cpp/)

匿名类是一个没有名字的类。C++ 支持这个特性。

*   这些类不能有构造函数，但可以有析构函数。
*   这些类既不能作为函数的参数传递，也不能用作函数的返回值。

**举例说明匿名类**

1.  **Creating single object of Anonymous Class :** In the first Example, Anonymous class is created with object name obj1\. The scope of the obj1 is throughout the program. So, we can access this into the main function. In main, using obj1, a call is given to member functions of the anonymous class.

    ```cpp
    // CPP program to illustrate 
    // concept of Anonymous Class
    #include <iostream>
    using namespace std;

    // Anonymous Class : Class is not having any name
    class
    {
        // data member
        int i; 
    public:
        void setData(int i)
        {
            // this pointer is used to differentiate
            // between data member and formal argument.
            this->i = i;
        }
        void print()
        {
            cout << "Value for i : " << this->i << endl;
        }

    } obj1;     // object for anonymous class

    // Driver function
    int main()
    {
        obj1.setData(10);
        obj1.print();
        return 0;
    }
    ```

    输出:

    ```cpp
    Value for i : 10

    ```

2.  **Creating two objects of Anonymous Class :** In the Second example, we have created two objects obj1 and obj2 for Anonymous class and given a call to member functions of the class. The scope of the obj1 and obj2 is through out the program. Likewise, we can create multiple objects for an anonymous class.

    ```cpp
    // CPP program to illustrate 
    // concept of Anonymous Class
    #include <iostream>
    using namespace std;

    // Anonymous Class : Class is not having any name
    class
    {
        // data member
        int i; 
    public:
        void setData(int i)
        {
            // this pointer is used to differentiate
            // between data member and formal argument.
            this->i = i;
        }
        void print()
        {
            cout << "Value for i : " << this->i << endl;
        }

    } obj1, obj2;    // multiple objects for anonymous class

    // Driver function
    int main()
    {
        obj1.setData(10);
        obj1.print();

        obj2.setData(20);
        obj2.print();
        return 0;
    }
    ```

    输出:

    ```cpp
    Value for i : 10
    Value for i : 20

    ```

3.  **Restricting the scope of Anonymous class :** To restrict the scope of the objects for the anonymous class, we can take a help of typedef. In the third example, by using **typedef** we can give a convenient name to class and use that name we have created multiple objects obje1 and obj2 for the anonymous class. Here we can control the scope of the obj1 and obj2 objects, which are inside the main function.

    ```cpp
    // CPP program to illustrate 
    // concept of Anonymous Class
    // by scope restriction
    #include<iostream>
    using namespace std;

    // Anonymous Class : Class is not having any name
    typedef class
    {
        // data member
        int i; 
    public:
        void setData(int i)
        {
            // this pointer is used to differentiate 
            // between data member and formal argument.
            this->i = i;
        }
        void print()
        {
            cout << "Value for i :" << this->i << endl;
        }

    } myClass;      // using typedef give a proper name

    // Driver function
    int main()
    {
        // multiple objects
        myClass obj1, obj2; 
        obj1.setData(10);
        obj1.print();

        obj2.setData(20);
        obj2.print();
        return 0;
    }
    ```

    输出:

    ```cpp
    Value for i : 10
    Value for i : 20

    ```