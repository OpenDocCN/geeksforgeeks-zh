# c++ 中的命名空间|集合 2(扩展命名空间和未命名的命名空间)

> 原文:[https://www . geesforgeks . org/namespace-in-c-set-2-extending-namespace-and-unnamed-namespace/](https://www.geeksforgeeks.org/namespace-in-c-set-2-extending-namespace-and-unnamed-namespace/)

我们已经在下面的集合 1 中引入了名称空间。

[c++ 中的命名空间|集合 1(简介)](https://www.geeksforgeeks.org/namespace-in-c/)

也可以在全局空间中创建多个名称空间。这可以通过两种方式实现。

*   **namespaces having different names**

    ```cpp
    // A C++ program to show more than one namespaces 
    // with different names.
    #include <iostream>
    using namespace std;

    // first name space
    namespace first
    {
       int func() {  return 5; }
    }

    // second name space
    namespace second
    {
       int func() { return 10; }
    }

    int main()
    {
       // member function of namespace
       // accessed using scope resolution operator
       cout << first::func() <<"\n";        
       cout << second::func() <<"\n"; 
       return 0;
    }
    ```

    输出:

    ```cpp
    5
    10

    ```

*   **Extending namespaces (Using same name twice)**
    It is also possible to create two namespace blocks having the same name. The second namespace block is nothing but actually the continuation of the first namespace. In simpler words, we can say that both the namespaces are not different but actually the same, which are being defined in parts.

    ```cpp
    // C++ program to demonstrate namespace exntension
    #include <iostream>
    using namespace std;

    // first name space
    namespace first 
    { 
       int val1 = 500;  
    }

    // rest part of the first namespace
    namespace  first 
    { 
       int val2 = 501;  
    }

    int main()
    {
       cout << first::val1 <<"\n";        
       cout << first::val2 <<"\n"; 
       return 0;
    }
    ```

    输出:

    ```cpp
    500
    501

    ```

**未命名的命名空间**

*   它们可在同一程序中直接使用，并用于声明唯一标识符。
*   在未命名的命名空间中，命名空间声明中未提及的命名空间的名称。
*   命名空间的名称由编译器唯一生成。
*   您创建的未命名命名空间只能在您在其中创建的文件中访问。
*   未命名的命名空间是变量静态声明的替代。

```cpp
// C++ program to demonstrate working of unnamed 
// namespaces
#include <iostream>
using namespace std;

// unnamed namespace declaration
namespace 
{
   int rel = 300; 
}

int main()
{
   cout << rel << "\n"; // prints 300
   return 0;
}
```

输出:

```cpp
300

```

本文由**阿比纳夫·蒂瓦里**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。