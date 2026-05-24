# C++ 中的对象委托

> 原文：[https://www.geeksforgeeks.org/object-delegation-in-cpp/](https://www.geeksforgeeks.org/object-delegation-in-cpp/)

## 简介

*   每种基于面向对象概念的编程语言都试图将一切与现实世界联系起来。
*   同样，C++ 语言使用 `class`、`inheritance`、`polymorphism` 来将概念与现实世界的概念联系起来。
*   本文将讨论 C++ 中的对象委托是什么以及对象委托在 C++ 中的用途。

## C++ 中的对象委托

对象委托是指使用另一个类的对象作为另一个类的类成员。这被称为对象委托。下面是委托的一些属性：

*   委托可以作为继承的替代方案，但在继承中存在“是一个”（is-a）关系，而在委托中，类之间没有继承关系。
*   委托允许我们在类中使用我们所需的特定类的属性。
*   委托可以被视为对象之间的一种关系，其中一个对象将方法调用转发给另一个对象，后者被称为其委托。
*   委托的主要优势是运行时的灵活性——委托可以在运行时轻松更改。
*   然而，与继承不同，大多数流行的面向对象语言并不直接支持委托，并且它不利于 `dynamic polymorphism`。

下面是说明对象委托的 C++ 程序：

```cpp
// C++ program to illustrate the
// Object Delegation
#include <iostream>
using namespace std;
class First {
public:
    void print() { cout << "The Delegate"; }
};
class Second {
    // Creating instance of the class
    First ob;

public:
    void print() { ob.print(); }
};

// Driver Code
int main()
{
    Second ob1;
    ob1.print();
    return 0;
}
```

**输出：**

```
The Delegate
```

## 什么时候用什么？

下面是一些使用继承或委托的例子：

*   假设类被称为 `B`，而派生/委托到的类被称为 `A`。
*   如果用户想要表达一种“是一个”（is-a）关系，则使用继承。
*   用户希望能够将该类传递给期望 `A` 的现有 API，然后使用继承。
*   用户想要增强 `A`，但 `A` 是 `final` 的，除了使用合成和委托外无法进一步细分。