# c++ 中静态函数可以虚化吗？

> 原文:[https://www.geeksforgeeks.org/g-fact-29/](https://www.geeksforgeeks.org/g-fact-29/)

在 C++ 中，一个类的*静态*成员函数不能是*虚拟的*。例如，下面的程序给出了编译错误。

```cpp
#include<iostream>

using namespace std;    

class Test
{
   public:
      // Error: Virtual member functions cannot be static      
      virtual static void fun()  { }
};
```

还有，*静态*成员函数不能是 *const* 和 *volatile* 。下面的代码在编译时也会失败。

```cpp
#include<iostream>

using namespace std;    

class Test
{
   public:
      // Error: Static member function cannot be const
      static void fun() const { } 
};
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。