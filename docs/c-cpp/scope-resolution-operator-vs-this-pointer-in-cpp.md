# c++ 中作用域解析运算符与该指针的关系

> 原文:[https://www . geesforgeks . org/scope-resolution-operator-vs-this-pointer-in-CPP/](https://www.geeksforgeeks.org/scope-resolution-operator-vs-this-pointer-in-cpp/)

**作用域解析运算符**用于访问静态或类成员，**该指针**用于在存在同名局部变量时访问对象成员。

考虑下面的 C++ 程序:

T3】CPPT5

```cpp
// C++ program to show that local parameters hide
// class members
#include <iostream>
using namespace std;

class Test {
    int a;

public:
    Test() { a = 1; }

    // Local parameter 'a' hides class member 'a'
    void func(int a) { cout << a; }
};

// Driver Code
int main()
{
    Test obj;
    int k = 3;
    obj.func(k);
    return 0;
}
```

T6T8**输出**T1

**解释:**上述程序的输出是 **3** ，因为“a”作为参数传递给了**函数**来隐藏类的“a”，即 1

然后如何输出类的' a '。这就是[这个指针](https://www.geeksforgeeks.org/this-pointer-in-c/)派上用场的地方。像 **cout < <这样的语句这- > a** 代替 **cout < < a** 可以简单地输出值 1，因为这个指针指向调用**函数**的对象。

## CPP

```cpp
// C++ program to show use of this to access member when
// there is a local variable with same name
#include <iostream>
using namespace std;
class Test {
    int a;

public:
    Test() { a = 1; }

    // Local parameter 'a' hides object's member
    // 'a', but we can access it using this.
    void func(int a) { cout << this->a; }
};

// Driver code
int main()
{
    Test obj;
    int k = 3;
    obj.func(k);
    return 0;
}
```

**输出**

```cpp
1
```

**怎么样** [**范围解析符**](https://www.geeksforgeeks.org/scope-resolution-operator-in-c/) **？**

我们不能使用上面示例中的范围解析运算符来打印对象的成员“a”，因为范围解析运算符只能用于静态数据成员(或类成员)。如果我们在上面的程序中使用范围解析操作符，我们会得到编译器错误，如果我们在下面的程序中使用这个指针，我们也会得到编译器错误。

## CPP

```cpp
// C++ program to show that scope resolution operator can be
// used to access static members when there is a local
// variable with same name
#include <iostream>
using namespace std;

class Test {
    static int a;

public:
    // Local parameter 'a' hides class member
    // 'a', but we can access it using ::
    void func(int a) { cout << Test::a; }
};

// In C++, static members must be explicitly defined
// like this
int Test::a = 1;

// Driver code
int main()
{
    Test obj;
    int k = 3;
    obj.func(k);
    return 0;
}
```

**输出**

```cpp
1
```

本文由**阿卡斯·萨其德瓦**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。