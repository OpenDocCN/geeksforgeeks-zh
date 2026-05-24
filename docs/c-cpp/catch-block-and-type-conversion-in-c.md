# c++ 中的 Catch 块和类型转换

> 原文:[https://www . geesforgeks . org/catch-block-and-type-conversion-in-c/](https://www.geeksforgeeks.org/catch-block-and-type-conversion-in-c/)

预测后续 C++ 程序的输出。

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    try
    {
        throw 'x';
    }
    catch(int x)
    {
        cout << " Caught int " << x;
    }
    catch(...)
    {
        cout << "Default catch block";
    }
}
```

**输出:**

```cpp
 Default catch block
```

在上面的程序中，一个字符' x '被抛出，并且有一个 catch 块来捕获一个 int。人们可能认为可以通过考虑 ASCII 值“x”来匹配 int catch 块。但是这种转换不会针对 catch 块执行。考虑下面的程序作为另一个例子，其中没有为抛出的对象调用转换构造函数。

## C++

```cpp
#include <iostream>
using namespace std;

class MyExcept1 {};

class MyExcept2
{
public:

    // Conversion constructor
    MyExcept2 (const MyExcept1 &e )
    {
        cout << "Conversion constructor called";
    }
};

int main()
{
    try
    {
        MyExcept1 myexp1;
        throw myexp1;
    }
    catch(MyExcept2 e2)
    {
        cout << "Caught MyExcept2 " << endl;
    }
    catch(...)
    {
        cout << " Default catch block " << endl;
    }
    return 0;
}
```

**输出:**

```cpp
Default catch block
```

顺便说一下，当引发派生对象并且有一个 catch 块来捕获基类型时，派生类型对象被转换为基类型。详见[本 GFact](https://www.geeksforgeeks.org/g-fact-60/) 。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。