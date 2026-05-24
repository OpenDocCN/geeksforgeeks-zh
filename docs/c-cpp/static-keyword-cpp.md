# c++ 中的静态关键字

> 原文:[https://www.geeksforgeeks.org/static-keyword-cpp/](https://www.geeksforgeeks.org/static-keyword-cpp/)

先决条件:[C 中的静态变量](https://www.geeksforgeeks.org/static-variables-in-c/)

静态关键字在与不同类型一起使用时有不同的含义。我们可以使用静态关键字:

**静态变量:**函数中的变量，类中的变量
**类的静态成员:**类中的对象和函数

现在让我们详细看看静态的每一种用法:

**静态变量**

*   **Static variables in a Function**: When a variable is declared as static, space for **it gets allocated for the lifetime of the program**. Even if the function is called multiple times, space for the static variable is allocated only once and the value of variable in the previous call gets carried through the next function call. This is useful for implementing [coroutines in C/C++ ](https://www.geeksforgeeks.org/coroutines-in-c-cpp/) or any other application where previous state of function needs to be stored.

    ```cpp
    // C++ program to demonstrate 
    // the use of static Static 
    // variables in a Function
    #include <iostream>
    #include <string>
    using namespace std;

    void demo()
    { 
        // static variable
        static int count = 0;
        cout << count << " ";

        // value is updated and
        // will be carried to next
        // function calls
        count++ ;
    }

    int main()
    {
        for (int i=0; i<5; i++)    
            demo();
        return 0;
    }
    ```

    输出:

    ```cpp
    0 1 2 3 4 

    ```

    您可以在上面的程序中看到变量计数被声明为静态的。所以，它的值是通过函数调用传递的。每次调用函数时，变量计数都不会初始化。
    顺便提一下， [Java 不允许函数](https://www.geeksforgeeks.org/g-fact-47/)中有静态局部变量。

*   **Static variables in a class**: As the variables declared as static are initialized only once as they are allocated space in separate static storage so, the static variables **in a class are shared by the objects.** There can not be multiple copies of same static variables for different objects. Also because of this reason static variables can not be initialized using constructors.

    ```cpp
    // C++ program to demonstrate static
    // variables inside a class

    #include<iostream>
    using namespace std;

    class GfG
    {
       public:
         static int i;

         GfG()
         {
            // Do nothing
         };
    };

    int main()
    {
      GfG obj1;
      GfG obj2;
      obj1.i =2;
      obj2.i = 3;

      // prints value of i
      cout << obj1.i<<" "<<obj2.i;   
    }
    ```

    您可以在上面的程序中看到，我们试图为多个对象创建静态变量 I 的多个副本。但这并没有发生。因此，类内的静态变量应该由用户使用类外的类名和范围解析运算符显式初始化，如下所示:

    ```cpp
    // C++ program to demonstrate static
    // variables inside a class

    #include<iostream>
    using namespace std;

    class GfG
    {
    public:
        static int i;

        GfG()
        {
            // Do nothing
        };
    };

    int GfG::i = 1;

    int main()
    {
        GfG obj;
        // prints value of i
        cout << obj.i; 
    }
    ```

    输出:

    ```cpp
    1

    ```

**类的静态成员**

*   **Class objects as static**: Just like variables, objects also when declared as static have a scope till the lifetime of program.
    Consider the below program where the object is non-static.

    ```cpp
    // CPP program to illustrate
    // when not using static keyword
    #include<iostream>
    using namespace std;

    class GfG
    {
        int i;
        public:
            GfG()
            {
                i = 0;
                cout << "Inside Constructor\n";
            }
            ~GfG()
            {
                cout << "Inside Destructor\n";
            }
    };

    int main()
    {
        int x = 0;
        if (x==0)
        {
            GfG obj;
        }
        cout << "End of main\n";
    }
    ```

    输出:

    ```cpp
    Inside Constructor
    Inside Destructor
    End of main

    ```

    在上面的程序中，对象在 if 块中声明为非静态的。因此，变量的范围只在 if 块中。因此，当对象被创建时，构造函数被调用，并且一旦 if 块的控制越过析构函数，就被调用，因为对象的范围在 if 块内，只是在它被声明的地方。
    现在让我们看看如果我们将对象声明为静态的，输出的变化。

    ```cpp
    // CPP program to illustrate
    // class objects as static
    #include<iostream>
    using namespace std;

    class GfG
    {
        int i = 0;

        public:
        GfG()
        {
            i = 0;
            cout << "Inside Constructor\n";
        }

        ~GfG()
        {
            cout << "Inside Destructor\n";
        }
    };

    int main()
    {
        int x = 0;
        if (x==0)
        {
            static GfG obj;
        }
        cout << "End of main\n";
    }
    ```

    输出:

    ```cpp
    Inside Constructor
    End of main
    Inside Destructor

    ```

    你可以清楚地看到输出的变化。现在析构函数在 main 结束后被调用。这是因为静态对象的范围贯穿了程序的生命周期。

*   **Static functions in a class**: Just like the static data members or static variables inside the class, static member functions also does not depend on object of class. We are allowed to invoke a static member function using the object and the ‘.’ operator but it is recommended to invoke the static members using the class name and the scope resolution operator.
    **Static member functions are allowed to access only the static data members or other static member functions**, they can not access the non-static data members or member functions of the class.

    ```cpp
    // C++ program to demonstrate static
    // member function in a class
    #include<iostream>
    using namespace std;

    class GfG
    {
       public:

        // static member function
        static void printMsg()
        {
            cout<<"Welcome to GfG!";
        }
    };

    // main function
    int main()
    {
        // invoking a static member function
        GfG::printMsg();
    }
    ```

    输出:

    ```cpp
    Welcome to GfG!

    ```

**相关文章:**

*   [静态关键词测验](https://www.geeksforgeeks.org/c-plus-plus-gq/static-keyword-gq/)
*   [c++ 中的静态数据成员](https://www.geeksforgeeks.org/stati/)
*   [静止物体什么时候被破坏？](https://www.geeksforgeeks.org/static-objects-destroyed/)
*   [关于静态成员函数的有趣事实](https://www.geeksforgeeks.org/some-interesting-facts-about-static-member-functions-in-c/)
*   [静态函数可以是虚函数吗？](https://www.geeksforgeeks.org/g-fact-29/)
*   [c++ 和 Java 中静态关键字的比较](https://www.geeksforgeeks.org/static-keyword-in-java/)
*   [C](https://www.geeksforgeeks.org/what-are-static-functions-in-c/)中的静态功能

本文由 **Harsh Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。