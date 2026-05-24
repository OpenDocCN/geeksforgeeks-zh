# `is_trivial` 是 C++ 中的平凡函数

> 原文: [https://www.geeksforgeeks.org/is_trivial-function-c/](https://www.geeksforgeeks.org/is_trivial-function-c/)

`is_trivial` 用于检查给定的 `T` 类型是否是平凡类。它是一个在 `<type_traits>` 头文件中声明的模板。平凡类型是一种类型，它的存储是连续的（通常是可复制的），并且只支持静态默认初始化（通常是可构造的），不管是 cv 限定的还是非 cv 限定的。它包括标量类型、平凡类以及任何此类类型的数组。

平凡类是一个类（用 `class`、`struct` 或 `union` 定义），它既可以平凡默认构造，也可以平凡复制，这意味着：
它使用隐式定义的默认值、复制和移动构造函数、复制和移动赋值以及析构函数。

*   它没有虚成员。
*   它没有带大括号或相等初始值设定项的非静态数据成员。
*   它的基类和非静态数据成员（如果有的话）本身也是平凡的类型。

`is_trivial` 从 `integral_constant` 继承为 `true_type` 或 `false_type`，具体取决于 `T` 是否是平凡类型。

**语法:**

```cpp
template <class T> struct is_trivial;
```

**示例:**

```cpp
std::is_trivial<T>::value
```

## 示例

```cpp
// CPP program to illustrate is_trivial function
#include <iostream>
#include <type_traits>
using namespace std;

class A {
};
class B {
    B() {}
};
class C : B {
};
class D {
    virtual void fn() {}
};

// Driver Code
int main()
{
    std::cout << std::boolalpha;
    // Returns value in boolean type
    std::cout << "A: " << std::is_trivial<A>::value << endl;
    std::cout << "B: " << std::is_trivial<B>::value << endl;
    std::cout << "C: " << std::is_trivial<C>::value << endl;
    std::cout << "D: " << std::is_trivial<D>::value << endl;
    return 0;
}
```

**输出**

```cpp
A: true
B: false
C: false
D: false
```

这里，`A` 是一个作为参数传递给函数 `is_trivial` 的类，它将返回一个整型常量 `bool` 的值，即 `true` 或 `false`。

本文由 **Mohak Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](http://www.write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。