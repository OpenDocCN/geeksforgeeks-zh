# 命名空间和类的区别

> 原文:[https://www.geeksforgeeks.org/difference-namespace-class/](https://www.geeksforgeeks.org/difference-namespace-class/)

类是数据类型。它们是[结构](https://www.geeksforgeeks.org/structures-c/)的扩展概念，它们可以包含数据成员，但也可以包含作为成员的函数，而**命名空间**只是将项目分组在一起的抽象方式。不能将[命名空间](https://www.geeksforgeeks.org/namespace-in-c/)创建为对象；把它当成一种命名惯例。它被用作区分相似函数、类、变量等的附加信息。不同的库中有相同的名称。本质上，命名空间定义了一个范围。以下是一些证明的要点:

1.命名空间是对标识符进行分组的一种方式，这样它们就不会发生冲突。使用类意味着您可以创建该类的实例，而对于命名空间则不是这样。

2.您可以对命名空间使用 using-declaration，除非从类派生，否则对类来说这是不可能的。

3.您可以重新打开一个名称空间，并跨翻译单元添加内容。你不能在课堂上这样做。例如:-

```cpp
namespace A {
int f1();
}

namespace A {
int f2();
}
```

是合法的，但是:

```cpp
class A {
    int f1();
};

class A { // illegal
    int f2();
};
```

不是。

4.可以有未命名的命名空间，但不能有未命名的类。例如:

```cpp
namespace { // fine

// some code....
}

class { // illegal
}
```

5.如果名称的长度使代码难以阅读，或者在不能使用指令的头文件中键入代码很繁琐，我们可以创建一个名称空间别名，作为实际名称的缩写。例如:

```cpp
#include <iostream>

namespace foo {
    namespace bar {
        namespace baz {
            int qux = 42;
        }
    }
}

namespace fbz = foo::bar::baz;

int main()
{
    std::cout << fbz::qux << '\n';
}
```

输出:

```cpp
 42 
```

在类的情况下，我们必须使用 typedef。

```cpp
class Car {
public:
    typedef std::vector<Wheel> WheelCollection;
    WheelCollection wheels;
};
```