# C++ 默认构造函数|内置类型

> 原文:[https://www . geesforgeks . org/c-default-constructor-内置类型/](https://www.geeksforgeeks.org/c-default-constructor-built-in-types/)

预测后续程序的输出？

```cpp
#include <iostream>
using namespace std;

int main() {

   cout << int() << endl;
   return 0;
}
```

没有任何参数或每个参数都有默认值的构造函数被视为*默认构造函数*。它将在需要时由编译器调用(确切地说，将根据需要为默认构造函数生成代码)。

*C++ 甚至允许内置类型(基元类型)拥有默认构造函数*。函数样式转换 *int()* 类似于将 0 转换为所需类型。程序在控制台上打印 0。

文章最初的内容引发了很多讨论，下面给出的是整理。

值得注意的是 C++ 中的引用与值语义以及 Plai n 旧数据类型的概念。从 Wiki 来看，原语类型和 [POD](http://en.wikipedia.org/wiki/Plain_old_data_structure) 类型没有用户定义的复制赋值运算符，没有用户定义的析构函数，也没有本身不是 PODs 的非静态数据成员。此外，POD 类必须是一个集合，这意味着它没有用户声明的构造函数，没有私有或非受保护的非静态数据，没有基类，也没有虚函数。

c++ 的创建者的一段摘录(来自一封邮件)“我认为你把‘实际的构造函数调用’和概念上有一个构造函数混淆了。内置类型被认为有构造函数”。

上面提到的代码片段 *int()* 被认为在概念上具有构造函数。但是，不会生成任何代码来使*成为显式的* *构造函数*调用。但是当我们观察程序集输出时，将生成代码来使用值语义初始化标识符。更多详情请参考本文件[第 8.5 节。](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2011/n3242.pdf)

感谢[普拉松·绍拉夫](http://stackoverflow.com/users/165520/prasoon-saurav)发起讨论，提供各种参考，修正我理解上的空白。

文基**投稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**

**参考文献:**

1.  **C++ programming language, 3e.**
***   [Latest C++ standard](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2011/n3242.pdf) -Section 8.5 of the working draft.**