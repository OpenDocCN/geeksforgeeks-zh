# 头文件和库的区别

> 原文:[https://www . geesforgeks . org/difference-header-file-library/](https://www.geeksforgeeks.org/difference-header-file-library/)

**头文件:**告诉编译器如何调用某些功能(不知道功能实际如何工作)的文件称为头文件。它们包含功能原型。它们还包含与库一起使用的数据类型和常数。我们使用 ***#include*** 在程序中使用这些头文件。这些文件以**结尾。h** 分机。

**库:**库是实现实际功能的地方，即包含功能体。库主要有两类:

*   static
*   Shared or dynamic

**静态:**静态库包含与最终用户应用程序链接的目标代码，然后它们成为可执行文件的一部分。这些库是在 ***编译时*** 专门使用的，这意味着当用户想要编译他/她的 C 或 C++ 程序时，库应该出现在正确的位置。在窗户上，它们以**结尾。lib** 扩展并带有**。a** 适用于 MacOS。

**共享或动态:**这些库只在 ***运行时*** 才需要，即用户无需使用这些库就可以编译自己的代码。简而言之，这些库在编译时被链接以解析未定义的引用，然后将其分发到应用程序，以便应用程序可以在运行时加载它。例如，当我们打开我们的游戏文件夹时，我们可以找到许多**。dll** (动态链接库)文件。由于这些库可以由多个程序共享，因此它们也被称为共享库。这些文件以**结尾。dll** 或**。lib** 扩展。在窗户里它们以。dll 扩展。

**示例:Math.h** 是一个头文件，其中包含了 sqrt()、pow()等函数调用的原型，而 **libm.lib** 、 **libmmd.lib** 、**libmmd.dll**则是一些数学库。简单来说，头文件就像名片，图书馆就像真人，所以我们用名片(头文件)去接触真人(图书馆)。

让我们以表格的形式来看看这两者的区别，这样就可以很容易地进行比较:

<figure class="table">

| 

头文件

 | 

库文件

 |
| --- | --- |
| They have extensions. h | They have an extension. lib |
| They contain function declarations and even macros. | They contain function definitions. |
| They are available in the "include subdirectory" of the Turbo compiler itself. | They are available in "lib subdirectory" in Turbo compiler. |
| The header file is human readable. Because they are in the form of source code. | The library is unreadable. Because they are in the form of machine code. |
| The header file in our program is included by using the command #include processed internally by the preprocessor. | The library files in our program are included in the special software called linker at the last stage. |

</figure>