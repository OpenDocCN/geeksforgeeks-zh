# c++ 类可以有自身类型的对象吗？

> 原文:[https://www . geeksforgeeks . org/can-a-c-class-have-a-object-of-self-type/](https://www.geeksforgeeks.org/can-a-c-class-have-an-object-of-self-type/)

类声明可以包含自身类型的静态对象，也可以有指向自身类型的指针，但不能有自身类型的非静态对象。

例如，以下程序运行良好。

```cpp
// A class can have a static member of self type
#include<iostream>

using namespace std;

class Test {
  static Test self;  // works fine

  /* other stuff in class*/ 

};

int main()
{
  Test t;
  getchar();
  return 0;
}
```

下面的程序也很好用。

```cpp
// A class can have a pointer to self type
#include<iostream>

using namespace std;

class Test {
  Test * self; //works fine

  /* other stuff in class*/ 

};

int main()
{
  Test t;
  getchar();
  return 0;
}
```

但以下程序产生编译错误“*字段‘self’的类型不完整*

```cpp
// A class cannot have non-static object(s) of self type.
#include<iostream>

using namespace std;

class Test {
  Test self; // Error

  /* other stuff in class*/ 

};

int main()
{
  Test t;
  getchar();
  return 0;
}
```

如果非静态对象是成员，那么类的声明是不完整的，编译器没有办法找出类的对象的大小。
静态变量不影响对象的大小。所以用自身类型的静态变量计算大小没有问题。
对于编译器来说，所有指针都有一个固定的大小，不管它们指向的数据类型是什么，所以这也没有问题。

感谢马尼什·贾恩和文基对这个职位的贡献。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。