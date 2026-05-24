# c++ 中的命名空间|集合 3(访问、创建头、嵌套和别名)

> 原文:[https://www . geesforgeks . org/namespace-c-set-3-creating-header-nesting-aliasing-access/](https://www.geeksforgeeks.org/namespace-c-set-3-creating-header-nesting-aliasing-accessing/)

[c++ 中的命名空间|集合 1(简介)](https://www.geeksforgeeks.org/namespace-in-c/)
[c++ 中的命名空间|集合 2(扩展命名空间和未命名的命名空间)](https://www.geeksforgeeks.org/namespace-in-c-set-2-extending-namespace-and-unnamed-namespace/)

<center>**Different ways to access namespace**</center>

In C++, there are two ways of accessing namespace variables and functions.

1.  **Normal way**

    ```cpp
    // C++ program to demonstrate accessing of variables
    // in normal way, i.e., using "::"
    #include <iostream>
    using namespace std;

    namespace geek
    {
        int rel = 300; 
    }

    int main()
    {
        // variable ‘rel’ accessed 
        // using scope resolution operator
        cout << geek::rel << "\n";  // prints 300

        return 0;
    }
    ```

    输出:

    ```cpp
    300

    ```

2.  **“using” directive**

    ```cpp
    // C++ program to demonstrate accessing of variables
    // in normal way, i.e., using "using" directive
    #include <iostream>
    using namespace std;

    namespace geek
    {
        int rel = 300; 
    }

    // use of ‘using’ directive
    using namespace geek;

    int main()
    {
       // variable ‘rel’ accessed 
       // without using scope resolution variable
       cout << rel << "\n";        //prints 300

       return 0;
    }
    ```

    输出:

    ```cpp
    300

    ```

<center>**Using namespace in header files**</center>

We can create namespace in one file and access contents using another program. This is done in the following manner.

*   我们需要创建两个文件。一个包含命名空间以及我们稍后要使用的所有数据成员和成员函数。
*   另一个程序可以直接调用第一个程序来使用其中的所有数据成员和成员函数。

**文件 1**

```cpp
// file1.h 
namespace foo
{
    int value() 
    { 
       return 5;    
    }
}
```

**文件 2**

```cpp
// file2.cpp - Not to be executed online
#include <iostream>
#include “file1.h” // Including file1
using namespace std;

int main () 
{
    cout << foo::value();
    return 0;
}
```

这里我们可以看到，命名空间是在 file1.h 中创建的，并且该命名空间的值()在 file2.cpp 中被调用。

<center>**Nested Namespaces**</center>

In C++, namespaces can also be nested i.e., one namespace inside another. The resolution of namespace variables is hierarchical.

```cpp
// C++ program to demonstrate nesting of namespaces
#include <iostream>
using namespace std;

// Nested namespace
namespace out
{
  int val = 5; 
  namespace in
  {
      int val2 = val;    
  }
}

// Driver code
int main()
{
  cout << out::in::val2;   // prints 5
  return 0;
}
```

输出:

```cpp
5

```

<center>**Namespace Aliasing**</center>

In C++, you can use an alias name for your namespace name, for ease of use. Existing namespaces can be aliased with new names, with the following syntax:

```cpp
namespace new_name = current_name;

```

```cpp
#include <iostream>

namespace name1 
{
    namespace name2 
    {
         namespace name3 
         {
             int var = 42;
         }
    }
}

// Aliasing 
namespace alias = name1::name2::name3;

int main()
{
    std::cout << alias::var << '\n';
}
```

输出:

```cpp
42

```

本文由 **[阿比纳夫·蒂瓦里](https://auth.geeksforgeeks.org/profile.php?user=Abhinav%20Tiwari&list=todoDone)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。