# c++ 中的内联函数

> 原文:[https://www.geeksforgeeks.org/inline-functions-cpp/](https://www.geeksforgeeks.org/inline-functions-cpp/)

内联函数是 C++ 的重要特性之一。那么，我们先来了解为什么使用内联函数，内联函数的目的是什么？

当程序执行函数调用指令时，中央处理器存储函数调用后指令的内存地址，将函数的参数复制到堆栈上，最后将控制权转移给指定的函数。然后，中央处理器执行函数代码，将函数返回值存储在预定义的存储单元/寄存器中，并将控制返回给调用函数。如果函数的执行时间小于从调用方函数到被调用方函数(被调用方)的切换时间，这可能会成为开销。对于大型和/或执行复杂任务的函数，与函数运行所花费的时间相比，函数调用的开销通常是微不足道的。然而，对于小的、常用的函数，进行函数调用所需的时间通常比实际执行函数代码所需的时间多得多。这种开销发生在小函数上，因为小函数的执行时间小于切换时间。

C++ 提供了内联函数来减少函数调用开销。内联函数是一个函数，当它被调用时，它是按行展开的。当内联函数被调用时，内联函数的整个代码在内联函数调用点被插入或替换。这种替换由 C++ 编译器在编译时执行。如果内联函数很小，它可能会提高效率。
内联定义函数的语法是:

```cpp
inline return-type function-name(parameters)
{
    // function code
}  
```

请记住，内联只是对编译器的请求，而不是命令。编译器可以忽略内联请求。编译器可能不会在以下情况下执行内联:
1)如果函数包含循环。(for，while，do-while)
2)如果函数包含静态变量。
3)如果一个函数是递归的。
4)如果函数返回类型不是 void，且函数体中不存在返回语句。
5)如果函数包含 switch 或 goto 语句。

**内联函数提供以下优势:**
1)不会产生函数调用开销。
2)还节省了调用函数时栈上推/弹出变量的开销。
3)它还节省了函数返回调用的开销。
4)当您内联一个函数时，您可以使编译器对函数体执行特定于上下文的优化。这种优化对于正常的函数调用是不可能的。其他优化可以通过考虑调用上下文和被调用上下文的流来获得。
5)内联函数可能对嵌入式系统有用(如果它很小的话)，因为内联可以产生比函数调用前导和返回更少的代码。

**内联函数缺点:**
1)内联函数增加的变量会消耗额外的寄存器，在内联函数之后，如果将要使用寄存器的变量数量增加，可能会增加寄存器变量资源利用率的开销。这意味着当内联函数体在函数调用点被替换时，函数使用的变量总数也会被插入。因此，用于变量的寄存器数量也会增加。因此，如果函数内联后变量数量急剧增加，那么肯定会导致寄存器使用的开销。

2)如果您使用了太多的内联函数，那么二进制可执行文件的大小将会很大，因为重复了相同的代码。

3)过多的内联也会降低指令缓存命中率，从而降低从缓存内存到主内存的取指令速度。

4)内联函数可能会增加编译时间开销如果有人更改了内联函数内部的代码，则必须重新编译所有调用位置，因为编译器需要再次替换所有代码以反映更改，否则将继续使用旧功能。

5)内联函数可能对许多嵌入式系统没有用处。因为在嵌入式系统中，代码大小比速度更重要。

6)内联函数可能会导致抖动，因为内联可能会增加二进制可执行文件的大小。内存抖动会导致计算机性能下降。

下面的程序演示了内联函数的用法。

```cpp
#include <iostream>
using namespace std;
inline int cube(int s)
{
    return s*s*s;
}
int main()
{
    cout << "The cube of 3 is: " << cube(3) << "\n";
    return 0;
} //Output: The cube of 3 is: 27
```

**内联函数和类:**
也可以在类内部定义内联函数。事实上，类中定义的所有函数都是隐式内联的。因此，内联函数的所有限制也适用于这里。如果需要在类中显式声明内联函数，那么只需在类内声明该函数，并使用 inline 关键字在类外定义它。
例如:

```cpp
class S
{
public:
    inline int square(int s) // redundant use of inline
    {
        // this function is automatically inline
        // function body
    }
};
```

上述风格被认为是一种不好的编程风格。最好的编程风格是只在类内编写函数的原型，并在函数定义中将其指定为内联。
例如:

```cpp
class S
{
public:
    int square(int s); // declare the function
};

inline int S::square(int s) // use inline prefix
{

}
```

以下程序演示了这一概念:

```cpp
#include <iostream>
using namespace std;
class operation
{
    int a,b,add,sub,mul;
    float div;
public:
    void get();
    void sum();
    void difference();
    void product();
    void division();
};
inline void operation :: get()
{
    cout << "Enter first value:";
    cin >> a;
    cout << "Enter second value:";
    cin >> b;
}

inline void operation :: sum()
{
    add = a+b;
    cout << "Addition of two numbers: " << a+b << "\n";
}

inline void operation :: difference()
{
    sub = a-b;
    cout << "Difference of two numbers: " << a-b << "\n";
}

inline void operation :: product()
{
    mul = a*b;
    cout << "Product of two numbers: " << a*b << "\n";
}

inline void operation ::division()
{
    div=a/b;
    cout<<"Division of two numbers: "<<a/b<<"\n" ;
}

int main()
{
    cout << "Program using inline function\n";
    operation s;
    s.get();
    s.sum();
    s.difference();
    s.product();
    s.division();
    return 0;
}
```

输出:

```cpp
Enter first value: 45
Enter second value: 15
Addition of two numbers: 60
Difference of two numbers: 30
Product of two numbers: 675
Division of two numbers: 3 
```

**宏有什么问题？**
熟悉 C 语言的读者都知道，C 语言使用宏。预处理器直接在宏代码中替换所有宏调用。建议始终使用内联函数而不是宏。根据 C++ 的创造者比雅尼·斯特劳斯特鲁普博士的说法，宏在 C++ 中几乎从来都不是必需的，而且它们容易出错。在 C++ 中使用宏有一些问题。宏无法访问类的私有成员。宏看起来像函数调用，但实际上不是。
示例:

```cpp
#include <iostream>
using namespace std;
class S
{
    int m;
public:
#define MAC(S::m)    // error
};
```

C++ 编译器检查内联函数的参数类型，并正确执行必要的转换。预处理器宏不能执行此操作。另一件事是宏由预处理器管理，内联函数由 C++ 编译器管理。

请记住:类内定义的所有函数都是隐式内联的，C++ 编译器会内联调用这些函数，但是如果函数是虚拟的，C++ 编译器就不能内联。原因是对虚函数的调用是在运行时而不是编译时解析的。虚拟意味着等到运行时，内联意味着在编译期间，如果编译器不知道将调用哪个函数，它如何执行内联？

另一件要记住的事情是，只有在函数调用期间花费的时间比函数体执行时间多的情况下，使函数内联才是有用的。内联函数完全不起作用的例子:

```cpp
inline void show()
{
    cout << "value of S = " << S << endl;
}
```

上述函数执行起来相对要花很长时间。一般来说，执行输入输出(I/O)操作的函数不应该被定义为内联的，因为它花费了大量的时间。从技术上讲，show()函数的内联价值有限，因为 I/O 语句花费的时间远远超过了函数调用的开销。

根据您使用的编译器，如果函数没有内联扩展，编译器可能会显示警告。像 Java & C#这样的编程语言不支持内联函数。
但是在 Java 中，编译器可以在调用小 final 方法时执行内联，因为 final 方法不能被子类覆盖，对 final 方法的调用是在编译时解析的。在 C#中，JIT 编译器还可以通过内联小函数调用来优化代码(就像在循环中调用小函数时替换它的主体)。

最后要记住的是，内联函数是 C++ 的宝贵特性。内联函数的适当使用可以提高性能，但是如果内联函数被任意使用，那么它们就不能提供更好的结果。换句话说，不要期望程序有更好的性能。不要让每个函数都内联。最好保持内联函数尽可能小。

**参考文献:**
1) [有效 C++，斯科特迈耶斯](http://www.flipkart.com/effective-c-55-specific-ways-improve-your-programs-designs-3rd/p/itmczzfe2gfvfuch?pid=9788131714805&affid=sandeepgfg)T5】2)[http://www.parashift.com/c++-faq/inline-and-perf.html](http://www.parashift.com/c++-faq/inline-and-perf.html)T8】3)[http://www.cplusplus.com/forum/articles/20600/](http://www.cplusplus.com/forum/articles/20600/)T11】4)[c++ 中的思维，第 1 卷，布鲁斯埃凯尔](http://www.flipkart.com/thinking-c-volume-1-with-cd/p/itmdwuafcz75hzjy?pid=9788131706619&affid=sandeepgfg)。
5) [C++ 完整参考，赫伯特·席尔德](http://www.flipkart.com/c-complete-reference/p/itmdwxz7nyaxabtj?pid=9780070532465&affid=sandeepgfg)

本文由**遇见普拉瓦西**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。