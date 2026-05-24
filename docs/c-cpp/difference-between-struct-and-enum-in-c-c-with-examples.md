# C/c++ 中结构和枚举的区别，示例

> 原文:[https://www . geesforgeks . org/struct-和 enum-in-c-c-with-examples/](https://www.geeksforgeeks.org/difference-between-struct-and-enum-in-c-c-with-examples/)

**<u>c++ 中的结构</u>**

A [结构](https://www.geeksforgeeks.org/structures-c/)是 C/C++ 中用户自定义的数据类型。结构创建的数据类型可用于将可能不同类型的项组合成单一类型。“struct”关键字用于创建结构。

**语法:**

> struct structureName{
> 
> 成员 1；
> 
> 成员 2；
> 
> 成员
> 
> 。
> 
> 。
> 
> 。
> 
> 成员们
> 
> };

C++ 中的结构可以包含两种类型的成员:

*   **数据成员**:这些成员都是正常的 C++ 变量。我们可以在 C++ 中用不同数据类型的变量创建一个结构。
*   **成员函数**:这些成员都是普通的 C++ 函数。除了变量，我们还可以在结构声明中包含函数。

**<u>c++ 中的枚举</u>**

[枚举](https://www.geeksforgeeks.org/enum-classes-in-c-and-their-advantage-over-enum-datatype/?ref=lbp)是枚举的简称。它是用户定义的数据类型。它用于定义可以选择的选项列表。一旦声明了 enum，我们就不能改变它的值，编译器会抛出一个错误。两个枚举不能共享相同的名称。

> enum enumName{
> 
> 成员 1；
> 
> 成员 2；
> 
> 成员
> 
> 。
> 
> 。
> 
> 。
> 
> 成员们
> 
> };

**<u>Struct 与 enum 的区别</u>**

<figure class="table">

| s No. | 结构体 | 列举型别 |
| --- | --- | --- |
| one | The "Struct" keyword is used to declare a structure. | The "Enum" keyword is used to declare Enum. |
| Two | The structure is a user-defined data type and a collection of different data types. | Enum is a collection that defines available options. |
| three | A structure can contain both data variables and methods. | Enumeration can only contain data types. |
| four | Structure supports private but unprotected access specifiers. | Enumeration has no private and protected access specifiers. |
| five | This structure cannot be inherited. | Enumeration also does not support inheritance. |
| six | Structure encapsulation is supported. | Enumeration does not support encapsulation. |
| seven | When a structure is declared, the value of its object can be modified. | Once an enumeration is declared, its value cannot be changed, otherwise the compiler will throw an error. |
| eight | Struct 只包含参数化的构造函数，没有析构函数。编译器不会为结构生成默认构造函数。 | Enumeration does not contain constructors and destructors. |
| nine | The value assigned to the structure is stored in stack memory. | Memory of enumerated data types is allocated in the stack. |

</figure>