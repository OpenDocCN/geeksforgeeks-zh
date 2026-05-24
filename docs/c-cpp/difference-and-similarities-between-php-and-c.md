# PHP 和 C 的异同

> 原文:[https://www . geesforgeks . org/PHP 和-c 之间的异同/](https://www.geeksforgeeks.org/difference-and-similarities-between-php-and-c/)

[PHP](https://www.geeksforgeeks.org/php/) 是一种专门为 web 开发设计的服务器端脚本语言。它可以很容易地嵌入到 HTML 文件中，HTML 代码也可以写在一个 PHP 文件中。PHP 与像 HTML 这样的客户端语言的区别在于，PHP 代码在服务器上执行，而 HTML 代码直接在浏览器上呈现。

[C](https://www.geeksforgeeks.org/c-programming-language/) 是一种过程编程语言。它最初是由丹尼斯·里奇作为系统编程语言开发的，用来编写操作系统。C 语言的主要特性包括对内存的低级访问、一组简单的关键字和干净的风格，这些特性使 C 语言适合像操作系统或编译器开发那样的系统编程。

**PHP 和 C 的相似之处**

| 因素 | 类似 |
| --- | --- |
| **语法** | 

1.  Code is insensitive to spaces.
2.  Semicolon is used to terminate a sentence.
3.  The function of is called in a similar way.
4.  Curly braces are used to enclose the code in a block.
5.  Support the annotation style of C and C++.

 |
| **操作员** | C 语言中所有类型的运算符在 PHP 中都有类似的行为，例如基本算术、布尔、赋值和比较运算符。 |
| **控制结构** | 

1.  Main control structures, such as if-else, while, for, do-while, have similar functions in these two languages.
2.  And Break continue are available in both PHP and C ..
3.  Switch is the same, except that strings are also accepted as case identifiers in PHP.

 |
| **功能原型** | 用户定义函数在两种语言中的命名方式相同。 |

<u>**PHP 和 C 的区别**</u>

| **参数** | 服务器端编程语言（Professional Hypertext Preprocessor 的缩写） | C |
| --- | --- | --- |
| **数据类型** | PHP has only two numerical data type:

*   整数(在 C 语言中可以比作长)
*   双(可与 C 中的双相比)

字符串的长度是随机的，在 PHP 中没有字符数据类型。 | c 有:

*   主数据类型（如 int、double、float、char、void 等。)
*   Derived data types (array, structure, union and pointer)

 |
| **类型转换** | 编译时不检查数据类型，很少出现数据类型错误。值和变量会自动转换为合适的数据类型。 | 在 C 语言中，变量是用数据类型声明的。虽然有些数据类型具有隐式转换，但其他数据类型需要进行类型转换。
数据类型错误常见于 C，要小心。 |
| **阵列** | 从表面上看，它们类似于 C.

*   The array in does not need to be pre-allocated or declared.
*   Index can be selected by user string or number.
*   They are used for hashing called associative arrays.

 | 

*   Arrays need to be allocated or declared in advance.
*   Their data types and memory allocation are completed before they are used in code.
*   Indicators can only be numbers starting from 0.

 |
| **结构** | 由于数组和对象，不需要结构类型。 | c 中存在结构类型。 |
| **原型** | PHP 中没有原型，因为函数在实现之前不需要声明。 | C 语言中有原型，因为函数在实现之前需要声明。 |
| **放纵** | 与 c 相比，PHP 要宽松得多。除了错误，犯新错误也会有意想不到的结果。 | 如果未声明数据类型、未声明数组大小等，c 将给出错误。
和 PHP 相比，稍微严格一点。 |