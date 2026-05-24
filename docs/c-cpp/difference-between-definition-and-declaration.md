# 定义与声明的区别

> 原文:[https://www . geesforgeks . org/定义与声明的区别/](https://www.geeksforgeeks.org/difference-between-definition-and-declaration/)

**变量的声明**用于通知编译器以下信息:变量的名称、它保存的值的类型以及它采用的初始值(如果有的话)。即声明给出了关于变量属性的细节。而变量的**定义**表示变量的存储位置。即在变量定义期间分配变量的内存。

在 C 语言中，变量的定义和声明同时发生。即声明和定义之间没有区别。例如，考虑以下声明

```cpp
int a;

```

这里，诸如变量名:a 和数据类型:int 之类的信息被发送到编译器，该编译器将存储在称为符号表的数据结构中。与此同时，将分配大小为 2 字节的内存(取决于编译器的类型)。

假设，如果我们只想声明变量而不想定义它，即我们不想分配内存，那么可以使用下面的声明

```cpp
extern int a;

```

在这个例子中，只发送关于变量的信息，不进行内存分配。上面的信息告诉编译器，变量 a 现在被声明，而变量 a 的内存稍后将在同一个文件或不同的文件中定义。

函数的声明为编译器提供了函数的名称、参数的数量和类型以及返回类型。例如，考虑以下代码，

```cpp
int add(int, int);

```

这里，一个名为 add 的函数用两个 int 类型的参数和返回 int 类型的参数声明。在此阶段不会分配内存。

函数的定义用于为函数分配内存。例如，考虑以下函数定义，

```cpp
int add(int a, int b)
  {
    return (a+b);
  }

```

在此函数定义期间，将分配函数添加的内存。一个变量或函数可以声明任意多次，但只能定义一次。

以上要点总结于下表， This declaration is just to inform the compiler that a function named f will be used in the function, and its return type and parameters are int.

| statement | Define |
| --- | --- |
| A variable or a function can be declared any number of times | A variable or a function can only be defined once |
| . When declared, memory | will be allocated |
| 

```cpp
int f(int a)
{
  return a;
} 

```

The system allocates memory by seeing the above function definition. |