# 防止 C++ 中的对象复制(3 种不同方式)

> 原文:[https://www . geesforgeks . org/proving-object-copy-in-CPP-3-异途/](https://www.geeksforgeeks.org/preventing-object-copy-in-cpp-3-different-ways/)

很多时候，用户希望一个 C++ 类的实例根本不应该被复制。那么，问题是我们如何实现这一点？

有三种方法可以实现这一点:

1.  **Keeping the Copy Constructor and Copy assignment operator as private in the class.**

    下面是 C++ 实现来说明如何做到这一点。

    ```cpp
    #include <iostream>
    using namespace std;

    class Base {
        int x;
    public:
        Base()    {  }
        Base(int y): x(y)     {  }
    private:

        // Copy constructor
        Base(const Base& obj) : x(obj.x) {   }

        // copy assignment operator
        Base& operator=(const Base& tmp_obj)
        {
            x = tmp_obj.x;
            return *this;
        }
    };

    int main()
    {
        Base b1(10);
        Base b2(b1); // calls copy constructor
        b2 = b1; // calls copy assignment operator
        return 0;
    }
    ```

    注意:这段代码不能编译，因为我们不能复制这个类的对象，所以它会显示这个错误。

    ```cpp
    prog.cpp: In function 'int main()':
    prog.cpp:18:2: error: 'Base::Base(const Base&)' is private
      Base(const Base &obj) : x(obj.x) //Copy constructor
      ^
    prog.cpp:33:12: error: within this context
      Base b2(b1); // Calls copy constructor
                ^
    prog.cpp:22:8: error: 'Base& Base::operator=(const Base&)' is private
      Base& operator = (const Base& tmp_obj) // copy assignment operator
            ^
    prog.cpp:35:5: error: within this context
      b2 = b1; // calls copy assignment operator
         ^

    ```

2.  **Inherit a Dummy class with a private copy constructor and a private copy assignment operator.**

    下面是 C++ 实现来说明如何做到这一点。

    ```cpp
    #include <iostream>
    using namespace std;

    class Dummy {
    public:
        Dummy() {  }
    private:
        Dummy(const Dummy& temp_obj)  {   }
        Dummy& operator=(const Dummy& temp_obj)   {   }
    };

    class Base : public Dummy {
        int x;
    public: 
        Base()  {   }
        Base(int y) : x(y)  {  }
    };

    int main()
    {
        Base b1(10);
        Base b2(b1); // Calls copy constructor
        b2 = b1; // Calls copy assignment operator
        return 0;
    }
    ```

    ```cpp
    prog.cpp: In function 'int main()':

    prog.cpp:12:5: error: 
    'Dummy::Dummy(const Dummy&)' is private
         Dummy(const Dummy &temp_obj)
         ^
    prog.cpp:22:7: error: within this context
     class Base: public Dummy
           ^
    prog.cpp:16:12: error: 
    'Dummy& Dummy::operator=(const Dummy&)' is private
         Dummy& operator = (const Dummy &temp_obj)
                ^
    prog.cpp:22:7: error: within this context
     class Base: public Dummy

    ```

    注意:这段代码不能编译，因为我们不能复制这个类的对象，所以它会显示这个错误。

3.  **Using Deleted copy constructor and copy assignment operator**: Above two ways are quite complex, C++ 11 has come up with a simpler solution i.e. just delete the copy constructor and assignment operator.

    下面是 C++ 实现来说明:

    ```cpp
    // CPP program to demonstrate use Delete copy
    // constructor and delete assignment operator
    #include <iostream>
    using namespace std;

    class Base {
        int x;
    public:
        Base()   {     }
        Base(int y) : x(y) {    }
        Base(const Base& temp_obj) = delete;
        Base& operator=(const Base& temp_obj) = delete;
    };

    int main()
    {
        Base b1(10);
        Base b2(b1); // Calls copy constructor
        b2 = b1; // Calls copy assignment operator
        return 0;
    }
    ```

    ```cpp
    prog.cpp: In function 'int main()':
    prog.cpp:24:15: error: use of deleted function
     'Base::Base(const Base&)'
         Base b2(b1); // Calls copy constructor
                   ^
    prog.cpp:16:5: note: declared here
         Base(const Base &temp_obj) = delete;
         ^
    prog.cpp:26:8: error: use of deleted function 
    'Base& Base::operator=(const Base&)'
         b2 = b1;  // Calls copy assignment operator
            ^
    prog.cpp:17:11: note: declared here
         Base& operator = (const Base &temp_obj) = delete;
               ^

    ```

    注意:这个代码不起作用，因为我们不能复制这个类的对象，因此它会显示这个错误。

 **参考:**
[https://ariya.io/2015/01/c-class-and-preventing-object-copy](https://ariya.io/2015/01/c-class-and-preventing-object-copy)

本文由 [**MAZHAR IMAM KHAN**](https://www.linkedin.com/in/mazhar-imam-khan-95a34ab3/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。