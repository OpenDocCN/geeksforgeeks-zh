# C 和嵌入式 C 有什么区别？

> 原文:[https://www . geeksforgeeks . org/c 和嵌入式 c 的区别是什么/](https://www.geeksforgeeks.org/what-are-the-differences-between-c-and-embedded-c/)

**[C 语言](https://www.geeksforgeeks.org/c-language-set-1-introduction/) :**
C 是一种通用编程语言，广泛用于设计任何类型的基于桌面的应用程序。它是由**丹尼斯·里奇**作为系统编程语言开发的操作系统。C 语言的主要特点包括对内存的低级访问、一组简单的关键字和整洁的风格，这些特点使 C 语言适合于操作系统或编译器开发等系统程序。本质上，它使用本地平台开发方案，即 it 应用程序的开发依赖于平台，只能在单个平台上使用。

**嵌入式 C:**
嵌入式 C 是 C 语言的扩展，用于开发基于微控制器的应用。嵌入式 C 语言对普通 C 编程语言的扩展是输入输出硬件寻址、定点算术运算、访问地址空间等。嵌入式 C 程序有五层基本结构。它们是:

*   **注释:**这些是简单易读的文本，用代码编写，让用户更容易理解。通常评论用 **//** 或 **/* */** 写。
*   **预处理器指令:**预处理器指令告诉编译器在哪些文件中查找程序中不存在的符号。
*   **全局声明:**定义全局变量的代码部分。
*   **局部声明:**定义局部变量的代码部分。
*   **主功能:**每个 C 程序都有一个驱动整个代码的主功能。它基本上有两个部分:声明部分和执行部分。其中，声明部分是声明所有变量的地方，执行部分定义了程序中执行的整个结构。

本质上它采用跨平台的开发方案，即它开发的应用是**平台无关的**，可以在多个平台上使用。

**C 与 Embedded C 的区别:**

<figure class="table">

*   GNU 编译集
*   博兰涡轮增压，
*   英特尔 C++ 软件

[T100**可用性和应用性**

*   C language has free-form programs.
*   Designed for desktop applications.
*   Optimization is normal.
*   C is very easy to read and modify.
*   It is very easy to fix bugs in C language programs.
*   Support other various programming languages when applying.
*   You can enter when the program is running.
*   Application of C program:
    *   logical program
    *   System software program

| parameter | C | 植入的 |
| --- | --- | --- |
| **通用** | 

*   它是一种高级语言。

 | 

*   嵌入式 C 只是一种扩展的 C 语言，用于开发基于微控制器的应用程序。
*   只是 c。

 |  |
| **依存关系** | 

*   c 语言是一种独立于硬件的语言。
*   c 编译器依赖于操作系统。

 | 

*   嵌入式 C 是一种完全依赖硬件的语言。
*   嵌入式 C 独立于操作系统。

 |
| **编译器** | 

*   对于 C 语言，标准编译器可以用来编译和执行程序。
*   执行 C 语言程序的流行编译器有:

 | 

*   对于嵌入式 C，
*   执行嵌入式 C 语言程序的流行编译器有:
    *   Keil 编译器
    *   BiPOM Electronic
    *   绿山软件

 |  |
| 

*   格式取决于所用微处理器的类型。
*   用于有限的资源，如内存和只读存储器。
*   高级优化。
*   嵌入式 C 语言不易阅读和修改。
*   在嵌入式 C 语言程序中，Bug 修复非常复杂。
*   只支持应用所需的处理器，不支持编程语言。
*   只有预定义的输入可以给正在运行的程序。
*   嵌入式 C 程序的应用；
    *   数字影碟
    *   电视
    *   数码相机

 |

</figure>