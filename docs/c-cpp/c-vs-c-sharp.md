# C++ vs C#

> 原文:[https://www.geeksforgeeks.org/c-vs-c-sharp/](https://www.geeksforgeeks.org/c-vs-c-sharp/)

[C#](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 是一种通用、现代、面向对象的编程语言，发音为“C sharp”。它是由安德斯·海尔斯伯格和他的团队领导的微软开发的。
[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 是一种静态类型、多参数和面向对象的编程语言。起初，C++ 被称为带类的 C。它是由比雅尼·斯特劳斯特鲁普在 AT & T 贝尔实验室开发的。

***下面是 C++ 和 C#的一些主要区别:***

<figure class="table">

| trait | C++ | c# |
| --- | --- | --- |
| **Memory management** | In c++, memory management is performed manually by programmers. If a programmer creates an object, he has the responsibility to destroy it after the task of the object is completed. | In C#, memory management is automatically performed by garbage collector. If the programmer creates an object, and after the task of the object is completed, the garbage collector will automatically delete the object. |
| **Platform dependency** | C++ code can run on any platform. C++ is used where applications need to communicate directly with hardware. | C# code is unique to windows. Although Microsoft is trying to make it global, so far, the major systems do not support C#. |
| **Multiple inheritance** | C++ supports multiple inheritance through classes. It means that a class can extend multiple classes at a time. | C# does not support any multiple inheritance through classes. |
| **Binding check** | In C++, binding checking is not performed by the compiler. The mistake is that if the programmer tries to access an invalid array index, it will give an incorrect result, but it will not show any compilation errors. | In C#, the binding check in the array is performed by the compiler. Wrong, if the programmer tries to access an invalid array index, it will give a compilation error. |
| **pointer** | In C++, the pointer can be used anywhere in the program. | In C#, pointers can only be used in unsafe mode. |
| **Language type** | C++ is a low-level language. | C# is a high-level object-oriented language. |
| **difficulty level** | C++ contains very complex features. | C# is quite easy because it has a well-defined class hierarchy. |
| **Application type** | C++ is usually used for console applications. | C# is used to develop mobile, window and console applications. |
| **Compile** | C++ code is directly converted into machine code after compilation. | C# code is translated into intermediate language code after compilation. |
| **Object-oriented** | C++ is not a purely object-oriented programming language because of its primitive data type. | C# is a pure object-oriented programming language. |
| **Access specifier** | Access modifiers are public, private and protected. It does not contain an internal & protected internal access modifier. | In C#, public, private, protected, internal & protected internal is used to access descriptors. |
| **Test variable** | In a switch statement, the test variable cannot be a string. | In the switch statement, the test variable can be a string. |
| **control statement** | It does not contain such additional flow control statements. | In addition to doing, doing at the same time; It has another flow control statement for each call. |
| **Function pointer** | It does have the concept of function pointer. | It has no concept of function pointer. |

</figure>