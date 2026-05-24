# 数据成员初始化

> 原文:[https://www.geeksforgeeks.org/g-fact-32/](https://www.geeksforgeeks.org/g-fact-32/)

在 C++ 中，类变量的初始化顺序与它们在类声明中出现的顺序相同。

考虑下面的代码。

```cpp
#include<iostream>

using namespace std;

class Test {
  private:    
    int y;
    int x;    
  public:
    Test() : x(10), y(x + 10) {}
    void print();
};

void Test::print()
{ 
   cout<<"x = "<<x<<" y = "<<y; 
}

int main()
{
    Test t;
    t.print();
    getchar();
    return 0;    
}
```

程序打印正确的 x 值，但是 y 值有些垃圾，因为 y 在 x 之前初始化，就像它在类声明中出现一样。

因此，可以使用以下两个版本中的一个来避免上述代码中的问题。

```cpp
// First: Change the order of declaration.
class Test {
  private:    
    int x;    
    int y;
  public:
    Test() : x(10), y(x + 10) {}
    void print();
};
```

```cpp
// Second: Change the order of initialization.
class Test {
  private:    
    int y;
    int x;    
  public:
    Test() : x(y-10), y(20) {}
    void print();
};
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。