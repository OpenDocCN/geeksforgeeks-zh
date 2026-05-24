# c++ 中的友元类和函数

> 原文:[https://www.geeksforgeeks.org/friend-class-function-cpp/](https://www.geeksforgeeks.org/friend-class-function-cpp/)

**朋友类**朋友类可以访问其他类的私有成员和受保护成员，在这些类中它被声明为朋友。有时允许特定类访问其他类的私有成员是有用的。例如，链接列表类可能被允许访问节点的私有成员。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
class Node {
private:
    int key;
    Node* next;
    /* Other members of Node Class */

    // Now class  LinkedList can
    // access private members of Node
    friend class LinkedList;
};
```

**好友功能**和好友类一样，好友功能可以被给予特殊授权，访问私有和受保护的成员。朋友函数可以是:
a)另一个类的成员
b)全局函数

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
class Node {
private:
    int key;
    Node* next;

    /* Other members of Node Class */
    friend int LinkedList::search();
    // Only search() of linkedList
    // can access internal members
};
```

以下是关于朋友函数和类的一些要点:
**(1)**朋友只能用于有限的目的。太多的函数或外部类被声明为具有受保护或私有数据的类的朋友，这降低了面向对象编程中封装单独类的价值。
**2)** 友谊不是相互的。如果 A 班是 B 的朋友，那么 B 不会自动成为 A 的朋友。
**3)** 友谊不是遗传的(详见[本](https://www.geeksforgeeks.org/g-fact-34/))
**4)**朋友的概念在 Java 中是不存在的。
**一个简单完整的 C++ 程序演示好友类**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
class A {
private:
    int a;

public:
    A() { a = 0; }
    friend class B; // Friend Class
};

class B {
private:
    int b;

public:
    void showA(A& x)
    {
        // Since B is friend of A, it can access
        // private members of A
        std::cout << "A::a=" << x.a;
    }
};

int main()
{
    A a;
    B b;
    b.showA(a);
    return 0;
}
```

输出:

```cpp
A::a=0
```

**一个简单完整的 C++ 程序演示另一个类的好友功能**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>

class B;

class A {
public:
    void showB(B&);
};

class B {
private:
    int b;

public:
    B() { b = 0; }
    friend void A::showB(B& x); // Friend function
};

void A::showB(B& x)
{
    // Since showB() is friend of B, it can
    // access private members of B
    std::cout << "B::b = " << x.b;
}

int main()
{
    A a;
    B x;
    a.showB(x);
    return 0;
}
```

输出:

```cpp
B::b = 0
```

**一个简单完整的 C++ 程序演示全球好友**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>

class A {
    int a;

public:
    A() { a = 0; }

    // global friend function
    friend void showA(A&);
};

void showA(A& x)
{
    // Since showA() is a friend, it can access
    // private members of A
    std::cout << "A::a=" << x.a;
}

int main()
{
    A a;
    showA(a);
    return 0;
}
```

输出:

```cpp
A::a = 0
```

**参考文献:**
[【http://en.wikipedia.org/wiki/Friend_class】](http://en.wikipedia.org/wiki/Friend_class)
[【http://en.wikipedia.org/wiki/Friend_function】](http://en.wikipedia.org/wiki/Friend_function)
[【http://www.cprogramming.com/tutorial/friends.html】](http://www.cprogramming.com/tutorial/friends.html)
[http://www.parashift.com/c++-faq/friends-and-encap.html](http://www.parashift.com/c++-faq/friends-and-encap.html)
如发现有不正确的地方，或想分享更多以上讨论话题的信息，请写评论。