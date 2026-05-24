# 内联命名空间和命名空间内“使用”指令的用法

> 原文:[https://www . geesforgeks . org/inline-namespace-usage-using-direction-inside-namespace/](https://www.geeksforgeeks.org/inline-namespaces-usage-using-directive-inside-namespaces/)

先决条件:[c++ 中的名称空间](https://www.geeksforgeeks.org/namespace-in-c/)
内联名称空间是在其原始名称空间定义中使用可选关键字 inline 的名称空间。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate working of
// inline namespaces
#include <iostream>
using namespace std;

namespace ns1
{
   inline namespace ns2
   {
       int var = 10;
   }
}

int main()
{
   cout << ns1::var;
   return 0;
}
```

**输出:**

```cpp
10
```

从上面的例子中我们可以看到，在许多情况下，内联命名空间的成员被视为封闭命名空间的成员(如下所列)。这个属性是可传递的:如果一个名字空间 N 包含一个内联名字空间 M，而内联名字空间 M 又包含一个内联名字空间 O，那么 O 的成员可以像它们是 M 或 N 的成员一样使用

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate working of
// inline namespaces inside inline namespaces

#include <iostream>
using namespace std;

namespace ns1
{
    inline namespace ns2
    {
        inline namespace ns3
        {
            int var = 10;
        }
    }
}

int main()
{
    cout << ns1::var;
    return 0;
}
```

**输出:**

```cpp
10
```

内联说明符使嵌套命名空间中的声明看起来就像是在封闭命名空间中声明的一样。这意味着它将声明(上例中的“var”)从嵌套的命名空间拖到包含的命名空间。
使用内联命名空间的优势:

*   **避免啰嗦:**考虑上面的代码，如果要打印“var”，就写:

```cpp
  cout << ns1::ns2::ns3::var;
```

*   只有当名称空间的名称像上面的例子一样短时，这看起来才是好的。但是通过将 inline 与名称空间一起使用，就不需要像上面给出的那样键入整个名称空间，也不需要使用“using”指令。
*   **对库的支持:**内联命名空间机制旨在通过提供一种支持某种形式版本控制的机制来支持库的演化。详见[本](http://www.stroustrup.com/C++ 11FAQ.html#inline-namespace)。

**“使用”指令**

这种相同的行为(与内联命名空间相同)也可以通过在命名空间中使用“使用”声明性来实现。命名内联命名空间的 using-指令隐式插入到封闭命名空间中(类似于未命名命名命名空间的隐式 using-指令)。考虑以下 C++ 代码:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate working
// of "using" to get the same effect as
// inline.
#include <iostream>
using namespace std;

namespace ns1
{
    namespace ns2
    {
        namespace ns3
        {
            int var = 10;
        }
        using namespace ns3;
    }

    using namespace ns2;
}

int main()
{
    cout << ns1::var;
    return 0;
}
```

**输出:**

```cpp
10
```

同样，using 指令使嵌套命名空间的声明看起来就像是在封闭命名空间中声明的一样。
**另见:** [命名空间的嵌套](https://www.geeksforgeeks.org/g-fact-62/)
**参考文献:**http://en.cppreference.com/w/cpp/language/namespace
本文由 **Arnav Shrivastava** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。