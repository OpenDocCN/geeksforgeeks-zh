# C 和客观 C 的区别

> 原文:[https://www . geeksforgeeks . org/c-与-objective-c/](https://www.geeksforgeeks.org/difference-between-c-and-objective-c/) 之间的差异

语言 **C** 是由**丹尼斯·里奇**在 20 世纪 70 年代早期为 **UNIX** 操作系统开发的。它是一种通用的过程编程语言。该语言用于开发系统应用程序和桌面应用程序。要了解更多关于 C 语言的知识，请参考 [https://www。极客们。org/c-编程-语言/](https://www. geeksforgeeks. org/c-programming-language/)

**目的 C** 是由**布拉德·考克斯**和**汤姆·洛夫**在 20 世纪 80 年代初**开发的。这是一种面向对象的通用语言，旨在为 C 编程语言提供闲聊式的消息传递。这种语言允许用户通过声明**类**来定义协议，数据成员可以成为**公共的**、**私有的**和**受保护的**。这种语言曾在苹果用于 **iOS** 和 **OS X** 操作系统。2014 年，苹果公司开发了 Swift 语言来取代这种语言。但是仍然有很多公司在维护他们用 objective C 写的遗留应用程序。**

> **C 和 Objective C 的主要区别在于，C 是一种不支持对象和类概念的过程编程语言，Objective C 是一种面向对象的语言，它包含了过程和面向对象编程语言的概念。**

**C 与客观 C 的区别:**

<figure class="table">

| C programming language | Objective C |
| --- | --- |
| It is a programming language oriented by **program** **. The problem is solved step by step.** | Objective C is a **object-oriented** programming language. It adds syntax and semantics that allow object-oriented languages. However, multiple inheritance attributes are not supported. |
| C language can be called a subset of Objective C | Objective C can be called a superset of C language. Besides C language, it also contains classes and objects. |
| The pointer used in C language is **vulnerable to** security attack | Language target C uses **null pointer** , so it is type-safe |
| compared with C. It is basically a low-level language of **assembly** . | Objective C is a kind of **high-level language** full of small talk, and the C. |
| C language does not combine any classes. The main purpose of developing C++ language in bjarne stroustrup is to add object-oriented features to C language, such as classes. | Objective C is an object-oriented language that combines classes and provides dynamic runtime. |
| It follows the programming mode of **top-down** . | It follows **bottom-up** programming method. |
| In this language, the big program code is the code that divides **into small pieces** s, which is called **function** . | In this language, large program codes are divided into smaller codes by **, which are called objects and **classes** .** |
| It only supports **pointer** . | supports **pointer** and **reference** . |
| Variables should declare at the beginning of the program **.** | In this language, variables can be declared anywhere in the program **.** |
| C language does not support **exception handling** | Target C supports **exception handling** , which can be implemented by **catch** and **try** blocks. |
| C It is not allowed to define **function** with **default parameter** . | It is allowed to define **function** with **default parameter** . |
| C **Can't run** Target C's code | Target C **can run** C's code. |
| C provides **malloc ()** and **calloc ()** functions for **dynamic memory allocation** , and deallocates | Target C provides **new operator** for memory allocation, **delete operator** for memory **deallocation** . |
| Data is **unsafe** in C language. | Using the concept of **encapsulation, security** |
| can be realized in target C. Its **does not have the **inline** function provided by** | **supports** **in-line** function. |
| C does not support **function** and **operator overload** . | Target C supports **functions** and **operator overloading** . |
| Generally speaking, it is called **function-driven** language. | It is called **Object-driven** language. |
| does not support **encapsulation, data hiding, inheritance, polymorphism** **abstraction** . | **Encapsulation, data hiding, inheritance, polymorphism** and **abstraction** are the key features of objective C. |
| C language **does not** | Target C **supports** **template** |
| This is good for **embedded services** . | is good for **networking and games** . |

</figure>