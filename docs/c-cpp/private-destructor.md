# 私有析构函数

> 原文:[https://www.geeksforgeeks.org/private-destructor/](https://www.geeksforgeeks.org/private-destructor/)

**也可以读作:**[c++ 中构造函数可以是私有的吗？](https://www.geeksforgeeks.org/can-constructor-private-cpp/)
**预测以下程序的输出。**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Private Destructor
#include <iostream>
using namespace std;

class Test {
private:
    ~Test() {}
};
int main()
{
}
```

以上程序编译运行良好。因此，我们可以说:创建私有析构函数是**而不是**编译器错误。
现在，你对下面的节目有什么看法。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Private Destructor
#include <iostream>
using namespace std;

class Test {
private:
    ~Test() {}
};
int main()
{
    Test t;
}
```

上述程序编译失败。编译器注意到局部变量“t”不能被析构，因为析构函数是私有的。
**现在，下面的节目呢？**T3】

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Private Destructor
#include <iostream>
using namespace std;

class Test {
private:
    ~Test() {}
};
int main()
{
    Test* t;
}
```

以上程序运行良好。没有正在构造的对象，程序只是创建了一个“Test *”类型的指针，所以没有任何东西被析构。
**接下来，下面的节目呢？**T3】

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Private Destructor

#include <iostream>
using namespace std;

class Test {
private:
    ~Test() {}
};
int main()
{
    Test* t = new Test;
}
```

上述程序也运行良好。当使用动态内存分配创建某个东西时，程序员有责任删除它。所以编译器不打扰。
**在析构函数被声明为私有的情况下，也可以使用 malloc()函数创建类的实例。**以下程序执行相同。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Private Destructor

#include <bits/stdc++.h>
using namespace std;

class Test {
public:
    Test() // Constructor
    {
        cout << "Constructor called\n";
    }

private:
    ~Test() // Private Destructor
    {
        cout << "Destructor called\n";
    }
};

int main()
{
    Test* t = (Test*)malloc(sizeof(Test));
    return 0;
}
```

**输出:**

但是，下面的程序编译失败。当我们调用 delete 时，会调用析构函数。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Private Destructor
#include <iostream>
using namespace std;

class Test {
private:
    ~Test() {}
};
int main()
{
    Test* t = new Test;
    delete t;
}
```

我们在上面的程序中注意到，当一个类有私有析构函数时，只能创建该类的动态对象。下面是一种方法**用私有析构函数创建类，并有一个作为类的朋友的函数。**该功能只能删除对象。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Private Destructor
#include <iostream>

// A class with private destructor
class Test {
private:
    ~Test() {}
public:
    friend void destructTest(Test*);
};

// Only this function can destruct objects of Test
void destructTest(Test* ptr)
{
    delete ptr;
}

int main()
{
    // create an object
    Test* ptr = new Test;

    // destruct the object
    destructTest(ptr);

    return 0;
}
```

**私有析构函数有什么用？**

每当我们想要控制一个类的对象的销毁时，我们就将析构函数设为私有。对于动态创建的对象，可能会发生这样的情况:您将指向该对象的指针传递给一个函数，而该函数会删除该对象。如果对象在函数调用后被引用，引用将变得悬空。详见[本](http://blogs.msdn.com/b/larryosterman/archive/2005/07/01/434684.aspx)。
如发现任何不正确的地方，请写评论，或者您想分享更多关于上述话题的信息