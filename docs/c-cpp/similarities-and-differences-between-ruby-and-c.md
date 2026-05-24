# 【Ruby 和 C++ 的异同

> 原文:[https://www . geesforgeks . org/ruby-and-c 的异同/](https://www.geeksforgeeks.org/similarities-and-differences-between-ruby-and-c/)

**c++ 和 Ruby 有很多相似之处，有些是:**

就像 C++ 一样，在 Ruby 中…

*   正如在 C++ 中一样，公共的、私有的和受保护的在 Ruby 中也同样有效。*   继承语法仍然只有一个字符，但是在 Ruby 中是*   C++ 中使用“名称空间”的方式，与我们在 ruby 中将代码放入“模块”的方式类似。*   Ruby 中有许多类似于 C++ 中的运算符。*   Though the keyword names have been changed to protect the innocent, exceptions work in a similar manner.

    【Ruby 和 C++ 的区别。

    | 【红宝石】 | c++ |
    | --- | --- |
    | In Ruby, each variable is just an automatically dereferenced name of an object, which means that there is no explicit reference in Ruby. | Unlike Ruby, there are explicit references in C++. |
    | Objects are strongly but dynamically typed in Ruby. | Objects are not as strongly typed as in Ruby. |
    | Call "constructor" instead of class name initialization. | C++ is not the case. |
    | Array and Hash are just two container types. | There are many container types in c++. |
    | C++ template is not required. No casting is required. | C++ template is needed here. Where is the casting? |
    | It's self that takes the place of this. | It is this that takes the place of self. |
    | The iteration is a little different. In Ruby, you don't use separate iterator objects. Instead, you use the iterator method of the container object, which takes a code block and passes successive elements to the code block. | Vector is necessary and used in C++, which makes coding easy. |
    | Lib, a unit test, comes standard with Ruby. | This is not available in C++. |
    | There is no type conversion in Ruby. | Type conversion is required in c++. |
    | There are some mandatory case practices. | There is no such use case convention in C++, which makes it easy. |
    | You can reopen a class at any time, or you can add more methods in Ruby. | We can't do this in C++. |
    | Some methods use "?" Or an ending "!" In ruby. It is actually part of the method name. | In C++, this symbol is not needed at the end of a method. |
    | All methods are virtual in Ruby. | Methods are not virtual in C++. |
    | Multithreading is built-in, but since Ruby 1.8, they are "green threads", not native threads. | There is no built-in multithreading in c++. |
    | Parentheses used to call methods are usually optional in Ruby. | Parentheses are both necessary and necessary in C++. |
    | Do not directly access member variables-all access to public member variables is done through the method. | Member variables in c++ can be accessed directly. |