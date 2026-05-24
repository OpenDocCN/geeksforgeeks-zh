# 【Ruby 与 C 语言的异同

> 原文:[https://www . geesforgeks . org/ruby 和 c 语言的异同/](https://www.geeksforgeeks.org/similarities-and-differences-between-ruby-and-c-language/)

### Ruby 和 C 语言的相似之处

C 和 Ruby 有很多相似之处，其中一些是:

像 C 一样，在 Ruby 中也…

*   如果程序员愿意，他们可以按程序编程。但是，在幕后，它仍然是面向对象的。*   这两种语言都有相同的运算符，例如复合赋值和按位运算符。但是 Ruby 不像 c 语言那样有++ 或者——*   他们俩都带了 __FILE__ 和 _ _ LINE _ _ 了。*   没有特殊的 const 关键字，但我们仍然可以有常数。*   在 C 和 Ruby 中，字符串都用双引号即“.”来表示。*   它们都包含可变字符串。*   使用 ri 命令，大多数文档都可以在你的终端上阅读，就像手册页一样。*   Samsort of the command-line debugger is available in both of them.

    ### The difference between Ruby and C language

    | Ruby | C |
    | --- | --- |
    | In Ruby, it can run directly without compiling code. | In C language, code compilation is necessary because it can't run directly. |
    | It requires "foo" instead of #include or # include "foo". | C. |
    | has no such requirement, and there is no variable declaration in Ruby. | Variable declaration is necessary in C. |
    | In Ruby, there is no macro or preprocessor, no cast, no pointer, no typedefs, sizeof and no enumeration available. | However, they exist in C. |
    | The parameters of methods (i.e. functions) are passed through values, where values are always object references. | In C language, functions are passed by value and by reference. |
    | The brackets used for method (i.e. function) calls are often optional. | This is not optional in C. |
    | . There is no char-they are just one-letter strings. | A Character uses char in C. |
    | Array text is placed in brackets, not braces in Ruby. | Array text is placed in brackets and cannot be dropped to assembly. | In C, you can't drop down to assembly. |
    | In Ruby, objects are strongly typed. | In C language, objects are not strongly typed. |
    | if and while conditional expressions do not use brackets. | The C language with if and while expressions needs parentheses. |
    | In Ruby, strings don't end with empty bytes. | And the string ends with a null byte in C. |
    | If you add two arrays, you will get a new larger array (allocated on the heap, of course), instead of doing pointer arithmetic. | C language needs pointer operation |
    | In Ruby, when you fill more elements into the array, the array will automatically become larger. | In C, the automatic array cannot become larger. |
    | All variables live on the heap. Besides, you don't need to release them yourself-the garbage collector will handle them. | In C, we need to release them ourselves, because there is no garbage collector in C. |
    | You usually don't use braces-just use the end keyword to end multi-line constructions (such as whileloops). | Braces are necessary, because ignoring braces will lead to grammatical errors. |
    | All functions and classes are defined in the main source code file, because there is no header file in ruby. | Header file appears in C. |
    | There is no semicolon to end the line. | There are closing lines. |
    | There is no definition of # in ruby. Use only constants. | # define in C. |
    | This do keyword is for the so-called "block". There is no "do statement" like that in C language. | Do statement is used in C language, which together with while forms a loop similar to do-while. |