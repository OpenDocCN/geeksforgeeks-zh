# c++ 中的三法则

> 原文:[https://www.geeksforgeeks.org/rule-of-three-in-cpp/](https://www.geeksforgeeks.org/rule-of-three-in-cpp/)

这个规则基本上说**如果一个类定义了下面的一个(或多个)，就应该明确定义这三个，分别是:**

*   破坏者
*   [复制构造器](https://www.geeksforgeeks.org/copy-constructor-in-cpp/)
*   [复制分配操作符](https://en.wikipedia.org/wiki/Assignment_operator_(C%2B%2B))

现在让我们试着理解为什么？
默认的构造函数和赋值运算符进行浅拷贝，当我们需要执行深拷贝时(例如，当一个类包含指向动态分配的资源的指针时)，我们创建自己的构造函数和赋值运算符。

首先，析构函数是做什么的？它包含每当对象被销毁时运行的代码。只影响对象的内容是没有用的。正在销毁的对象不能有任何更改。因此，析构函数会影响程序的整体状态。

现在，假设我们的类没有复制构造函数。复制对象会将其所有数据成员复制到目标对象。在这种情况下，当对象被销毁时，析构函数运行两次。析构函数对于每个被销毁的对象也有相同的信息。在没有适当定义的复制构造函数的情况下，析构函数应该只执行一次，却执行了两次。这种重复执行是麻烦的来源。

下面是一个编码示例:

## C++

```cpp
// In the below C++ code, we have created
// a destructor, but no copy constructor
// and no copy assignment operator.
class Array
{
private:
    int size;
    int* vals; 

public:
    ~Array();
    Array( int s, int* v );
};

Array::~Array()
{
   delete vals;
   vals = NULL;
}

Array::Array( int s, int* v )
{
    size = s;
    vals = new int[ size ];
    std::copy( v, v + size, vals );
}

int main()
{
   int vals[ 4 ] = { 11, 22, 33, 44 };
   Array a1( 4, vals );

   // This line causes problems.
   Array a2( a1 );

   return 0;
}
```

在上面的例子中，一旦程序超出范围，类析构函数就被调用，不是一次，而是两次。首先是因为删除了 a1，然后是 a2。默认的复制构造函数复制指针*val*，不为其分配内存。因此，删除 a1 时，析构函数释放*val*。所有后续的包含试图被析构函数删除的实例的*val*导致程序崩溃，因为*val*不再存在。

这与[拷贝分配操作符](https://en.wikipedia.org/wiki/Assignment_operator_(C%2B%2B))的情况类似。如果一个类没有显式定义的赋值运算符，则将发生所有源数据成员到目标相应数据成员的隐式赋值。总之，它会创建一个副本，这也是前面定义的相同问题。

**参考文献:**

*   [https://en . Wikipedia . org/wiki/Rule _ of _ three _(C % 2B % 2B _ 编程)](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming))
*   [http://www . drdobbs . com/c-made-easy-the-rule-of-three/184401400](http://www.drdobbs.com/c-made-easier-the-rule-of-three/184401400)

本文由**尼哈尔·兰詹·萨卡尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。