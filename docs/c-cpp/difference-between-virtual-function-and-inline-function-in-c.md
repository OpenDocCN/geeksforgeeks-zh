# c++ 中虚函数和内联函数的区别

> 原文:[https://www . geesforgeks . org/虚函数和内联函数的区别在 c/](https://www.geeksforgeeks.org/difference-between-virtual-function-and-inline-function-in-c/)

[**虚函数:**](https://www.geeksforgeeks.org/virtual-function-cpp/) 虚函数是在基类内声明的成员函数，由派生类重新定义。

[**内联函数:**](https://www.geeksforgeeks.org/inline-functions-cpp/) 内联函数是一个由关键字 Inline 定义的普通函数，它是一个由编译器扩展的短函数，其参数只计算一次。

在 C++ 中内联定义函数的语法是:

```cpp
inline return-type function-name(parameters)
{
    // function code
} 
```

**虚函数与内联函数的区别如下:**

<figure class="table">T53】7。内联函数用于减少函数调用开销。

| **虚函数** | **内联函数** |
| 1。 Virtual functions must be declared in the public part of the class. | 1。 Inline function is a common function defined by the keyword inline. |
| 2。 Virtual functions cannot be static. | 2。 Inline functions can also be non-static. |
| 3。 Virtual functions are defined in the base class. | 3。 Inline functions are short-length functions, and they automatically become inline functions without using inline keywords in classes. |
| 4。 Virtual functions reduce the efficiency of code. | 4。 Inline functions are used to improve the efficiency of code. |
| 5。 Virtual function is runtime polymorphism. | 5。 Inline functions are for compile-time polymorphism. |
| 6。 A virtual function can consist of a virtual destructor, but it cannot have a virtual constructor. | 6。 Inline functions can also be composed of inline constructors. |
| 7。 Virtual can be used for dynamic linking. |

</figure>