# 移除 C++ 17 的特性

> 原文:[https://www.geeksforgeeks.org/removed-features-of-cpp17/](https://www.geeksforgeeks.org/removed-features-of-cpp17/)

[C++ 17](https://www.geeksforgeeks.org/features-of-c17-with-examples/) 支持编写简单、清晰、更具表现力的代码。C++ 17 中引入的一些特性有:

*   Nested namespace
*   And variable declarations in switch.
*   if constexpr 语句
*   Structured binding
*   Collapse expression
*   Enumeration's direct list initialization

随着 C++ 17 的新版本，引入了许多新功能，但一些功能被删除或弃用。下面列出了这些操作:

*   Delete the deprecated operator++
*   Delete register
*   删除 auto_ptr
*   trigger
*   阿云(类型)
*   Std::function in the distributor is supported
*   标准::指针指向一元函数和标准::指针指向活页夹函数
*   标准::活页夹 1 ST 和标准::第二个活页夹
*   标准::绑定 1 和神学博士。

让我们开始详细讨论这些功能。

**1。删除不推荐使用的运算符++ :** [后缀和前缀增量(++)表达式](https://www.geeksforgeeks.org/pre-increment-and-post-increment-in-c/)现在对 [bool](https://www.geeksforgeeks.org/bool-data-type-in-c/) 操作数无效，因为 bool 类型的前缀和后缀运算符++ [重载了](https://www.geeksforgeeks.org/operator-overloading-c/)，但在这两种情况下，bool 参数的返回值都是真的。bool 类型不支持全套算术类型。自从 [C++ 98](https://www.geeksforgeeks.org/history-of-c/) 推出以来，这个变化就一直在等待。在 C++ 17 的新版本中，它不再被视为算术类型，这些运算符已被弃用。

**替代品:****STD::exchange**可用作此替代品，但仅限于后缀[运算符](https://www.geeksforgeeks.org/operators-c-c/)具有有效用途的情况。交换函数用新值替换对象的值，并返回对象的旧值。

**2。寄存器删除:**早在 C++ 11 中[寄存器关键字](https://www.geeksforgeeks.org/understanding-register-keyword/)就被弃用了。register 关键字指定或给[编译器](https://www.geeksforgeeks.org/phases-of-a-compiler/)一个提示，即[变量](https://www.geeksforgeeks.org/variables-in-c/)可以放在寄存器中进行快速访问，或者这些变量可能被大量使用，这样它可以通过将它们存储在 CPU 寄存器中来进行优化。但是编译器会进行隐式优化，并且很少使用这个提示。因此，在新版本中，register 关键字被删除，尽管该关键字仍保留给未来的版本。

**语法:**

```cpp
register string s = "Register on GfG"
```

**替代项:**没有注册的替代项，因为编译器会自动执行相同的工作。

**3。移除 auto_ptr:** [auto_ptr](https://www.geeksforgeeks.org/auto_ptr-unique_ptr-shared_ptr-weak_ptr-2/) 用于创建智能[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)，以处理[对象的](https://www.geeksforgeeks.org/c-classes-and-objects/)生存期。它是它所指的对象的所有者。当一个物体被摧毁时， **auto_ptr** 也会自动被摧毁。这个[智能指针](https://www.geeksforgeeks.org/smart-pointers-cpp/)在它的[复制构造函数](https://www.geeksforgeeks.org/copy-constructor-in-cpp/)中悄悄窃取托管对象的所有权，并从右边的参数中复制赋值。因此，副本与原始智能指针对象不同。由于这些复制语义， **auto_ptr** 不能作为**copy constructionable**工作，因此不推荐使用。

**替代品:****auto _ ptr**很容易被、**T5】unique _ ptr**T8 所取代，这也是一款智能指针，功能类似，但安全性更高。它在 C++ 11 中被引入作为 **auto_ptr** 的直接替代，因为它提供了新的特性(删除)和对数组的支持。此外，它只允许引用指针的一个所有者。因此，在使用 **unique_ptr** 时，一个资源最多只能有一个 **unique_ptr** ，当该资源被销毁时，该资源将被自动认领。如果试图复制 **unique_ptr** ，则会导致[编译时错误](https://www.geeksforgeeks.org/difference-between-compile-time-errors-and-runtime-errors/)。****

****例:****

```cpp
unique_ptr<T> p1 (new T);
unique_ptr<T> p2 = p1; 
// Error: can't copy unique_ptr
```

****4。三联画:**三联画是一组三个[人物](https://www.geeksforgeeks.org/character-arithmetic-c-c/)。基本上，它是一个特殊的字符序列，用作某些字符的替代。它由两个问号表示。**

****例:****

```cpp
??- produces ~ 
??= produces #
??/ produces \
??’ produces ^
??( produces [
??) produces ]
??! produces |
??< produces {
??> produces }
```

**但是它们会产生很多混乱，因为它们在注释之前被解析，因此在最新版本中被删除。**

****替代品:**c++ 17 没有为 Trigraph 提供任何替代品，因为现代键盘具备所有这些功能。此外，它还会在代码中产生许多错误。**

****5。throw(typeid):** 如果任何[函数](https://www.geeksforgeeks.org/functions-in-c/)被声明为其异常规范中列出的类型 T，则该函数可能会向该类型或从其派生的类型抛出异常。这是动态异常规范的非抛出版本，已被弃用，现已删除。已经换成了**不例外**含义更明确。**

****语法:****

```cpp
throw(typeid, typeid, ...)
```

****例:****

```cpp
void throwsInt(int x) throw(int) 
{  
    cout<<"throw function replaced with noexcept :)";  
    if (x == 0) 
       { 
      throw 1;  
       }
} 
```

****替代品:**如上所述，投掷可以有更好的替代品**不例外**。它指定了[功能](https://www.geeksforgeeks.org/functions-in-c/)是否可以抛出[异常](https://www.geeksforgeeks.org/exception-handling-c/)而不指定它们的类型。但是只有在函数调用不能抛出任何错误时才使用它，否则，程序将终止。**

****6。std::函数中的分配器支持:**几个[构造函数](https://www.geeksforgeeks.org/constructors-c/)允许指定一个[分配器](https://www.geeksforgeeks.org/stdallocator-in-cpp-with-examples/)用于分配内部内存。std::function 也有接受分配器参数的构造函数，但语义不清楚，并且在类型擦除上下文中存储分配器，然后稍后恢复该分配器以进行复制分配期间所需的任何分配时，会出现技术故障。因此，这些[构造函数重载](https://www.geeksforgeeks.org/constructor-overloading-c/)在 C++ 17 中被移除了。**

****替代品:**在取代分配器的 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中没有这样的特性。**

****7。std::pointer_to_unary_function，STD::pointer _ to _ binary _ function:STD::pointer _ to _ unary _ function**，**STD::pointer _ to _ binary _ function**充当一元或二元函数的包装器的函数对象。这些函数包括一个**构造器**，它用提供的函数和调用存储函数的运算符()函数构造一个新的**指向一元函数的指针**对象。**

****替代项:**这两个函数 **std::function** 和 **std::ref** 取代了**STD::pointer _ to _ unary _ function**、**STD::pointer _ to _ binary _ function**。**

****8。std::binder1st 和 std::binder2nd:** 这是将参数绑定到二进制函数的函数对象。参数的值在构造时传递给对象，并存储在对象中。每当通过[运算符()函数](https://www.geeksforgeeks.org/operator-overloading-c/)调用函数对象时，存储的值作为参数之一传递，另一个参数作为运算符()的参数传递。得到的函数对象是一元函数。**

***   **Binder 1st:** Bind the first parameter to the value given when building the object.*   **Binder 2nd:** Bind the second parameter to the value given when constructing the object.**

****替代品:****Lambdas****STD::bind**是可以作为 binder1st 和 binder2nd 替代品的两个特性。**

****9。std::bind1st 和 std::bind2nd:** 这些是创建 STD::bind 1 ST 或 std::bind2nd 实例的辅助函数，它们将给定参数绑定到给定二进制函数对象的第一个或第二个参数。但是，在 C++ 11 中引入 lambdas 后，这些都没有用了，因此它们被弃用了。**

****10。其他功能:****

*   **【STD::mem _ fun _ t】，**
*   **【STD::mem _ fun 1 _ t】**
*   **【STD::const _ mem _ fun _ t】**
*   **【STD::const _ mem _ fun 1 _ t】**

**这些是函数对象，将指针包装到没有[参数或只有一个参数的成员函数。](https://www.geeksforgeeks.org/parameter-passing-techniques-in-c-cpp/)[类](https://www.geeksforgeeks.org/c-classes-and-objects/)实例，其要调用的成员函数作为指向操作符()的指针传递，即其要调用的成员函数通过指向后者的调用操作符的指针传递的对象，作为引用传递。不推荐使用它们，因为它们仅限于没有参数或只有一个参数的成员函数，并且需要不同的函数和函数对象来处理指向类实例的指针或引用。**

****替代项:**上述函数的替代项是 **std::mem_fn** ，它可以处理任意数量变量的成员函数，不仅可以处理对对象的引用或指针，还可以处理智能指针。**