# 为什么 C++ 中空类的大小不为零？

> 原文:[https://www . geesforgeks . org/为什么空类的大小不是 c 中的零/](https://www.geeksforgeeks.org/why-is-the-size-of-an-empty-class-not-zero-in-c/)

C 中引入结构时，当时还没有[对象](https://www.geeksforgeeks.org/c-classes-and-objects/)的概念。因此，根据 C 标准，决定将空结构的大小保持为零。

在 C++ 中，空结构/类的大小是**一个字节**至于调用一个函数，至少空结构/类应该有一些大小( ***至少需要 1 个字节*** )即一个字节使它们可区分。

现在要了解一个空班级的规模，我们先来学习什么是空班级吧！

**空类:**是不包含任何数据成员(如 int a、float b、char c、string d 等)的类。)但是，空类可能包含成员函数。

### **为什么 C++ 中的一个空类实际上占用一个字节？**

简单地说，没有对象的类不需要分配空间。该空间是在类被实例化时分配的，因此编译器将 1 个字节分配给一个空类的对象，以获得其唯一的地址标识。

如果一个类有多个对象，它们可以有不同的唯一内存位置。假设，如果一个类没有任何大小，那么在内存位置会存储什么？这就是为什么当我们在 C++ 程序中创建一个空类的对象时，它需要一些内存来存储，并且可以保留的最小内存量是 1 字节。因此，如果我们创建一个空类的多个对象，每个对象都将有一个唯一的地址。

***下面的代码显示了空类的大小:***

## CPP

```cpp
// C++ program without any compilation
// error to demonstrate the size of
// an Empty Class
#include <iostream>
using namespace std;

// Creating an Empty Class
class Empty_class {
};

// Driver Code
int main()
{
    cout << "Size of Empty Class is = "
         << sizeof(Empty_class);
    return 0;
}
```

**输出**

```cpp
Size of Empty Class is = 1
```

空类的大小不为零。一般为 1 字节。确保两个不同的对象具有不同的地址是非零的。请参见以下示例。

## CPP

```cpp
// C++ program without any compilation
// error to demonstrate that the size
// of the two different objects of an
// Empty Class will have different
// addresses
#include <iostream>
using namespace std;

// Creating an Empty class
class Empty {
};

// Driver Code
int main()
{
    Empty a, b;

    if (&a == &b)
        cout << "Impossible " << endl;
    else
        cout << "Fine " << endl;

    return 0;
}
```

**输出**

```cpp
Fine 
```

出于同样的原因(不同的对象应该有不同的地址)，**“新”**总是返回指向不同对象的指针。请参见以下示例。

## c++

```cpp
// C++ program without any
// compilation error to demonstrate
// that "new" always returns pointers
// to distinct objects
#include <iostream>
using namespace std;

// Creating an Empty Class
class Empty {
};

// Driver Code
int main()
{
    Empty* p1 = new Empty;
    Empty* p2 = new Empty;

    if (p1 == p2)
        cout << "Impossible " << endl;
    else
        cout << "Fine " << endl;

    return 0;
}
```

**输出**

```cpp
Fine 
```

现在，猜测以下程序的输出:

## CPP

```cpp
// CPP Program as an exercise

#include <iostream>
using namespace std;

// Creating an Empty Class
class Empty {
};

// Creating a Derived Class
class Derived : Empty {
    int a;
};

// Driver Code
int main()
{
    cout << sizeof(Derived);
    return 0;
}
```

**Output**

```cpp
4
```

> **注:**输出不大于 4。有一个有趣的规则说空基类不需要用单独的字节来表示。因此编译器可以在基类为空的情况下自由地进行优化。

作为练习，请在您的编译器上尝试以下程序。

## CPP

```cpp
// CPP Program as an exercise
#include <iostream>
using namespace std;

class Empty {
};

class Derived1 : public Empty {
};

class Derived2 : virtual public Empty {
};

class Derived3 : public Empty {
    char c;
};

class Derived4 : virtual public Empty {
    char c;
};

class Dummy {
    char c;
};

int main()
{
    cout << "sizeof(Empty) " << sizeof(Empty) << endl;
    cout << "sizeof(Derived1) " << sizeof(Derived1) << endl;
    cout << "sizeof(Derived2) " << sizeof(Derived2) << endl;
    cout << "sizeof(Derived3) " << sizeof(Derived3) << endl;
    cout << "sizeof(Derived4) " << sizeof(Derived4) << endl;
    cout << "sizeof(Dummy) " << sizeof(Dummy) << endl;

    return 0;
}
```

**输出**

```cpp
sizeof(Empty) 1
sizeof(Derived1) 1
sizeof(Derived2) 8
sizeof(Derived3) 1
sizeof(Derived4) 16
sizeof(Dummy) 1
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。