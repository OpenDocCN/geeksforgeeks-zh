# 定义与声明的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-definition-and-declaration/](https://www.geeksforgeeks.org/difference-between-definition-and-declaration/)

**变量的声明**用于通知编译器以下信息：变量的名称、它保存的值的类型以及它采用的初始值（如果有的话）。即声明给出了关于变量属性的细节。而变量的**定义**表示变量的存储位置。即在变量定义期间分配变量的内存。

在 C 语言中，变量的定义和声明同时发生。即声明和定义之间没有区别。例如，考虑以下声明：

```cpp
int a;
```

这里，诸如`变量名:a`和`数据类型:int`之类的信息被发送到编译器，该编译器将存储在称为`符号表`的数据结构中。与此同时，将分配大小为 2 字节的内存（取决于编译器的类型）。

假设，如果我们只想声明变量而不想定义它，即我们不想分配内存，那么可以使用下面的声明：

```cpp
extern int a;
```

在这个例子中，只发送关于变量的信息，不进行内存分配。上面的信息告诉编译器，变量`a`现在被声明，而变量`a`的内存稍后将在同一个文件或不同的文件中定义。

函数的声明为编译器提供了函数的名称、参数的数量和类型以及返回类型。例如，考虑以下代码：

```cpp
int add(int, int);
```

这里，一个名为`add`的函数用两个`int`类型的参数和返回`int`类型的参数声明。在此阶段不会分配内存。

函数的定义用于为函数分配内存。例如，考虑以下函数定义：

```cpp
int add(int a, int b)
{
    return (a+b);
}
```

在此函数定义期间，将分配函数`add`的内存。一个变量或函数可以声明任意多次，但只能定义一次。

以上要点总结于下表，This declaration is just to inform the compiler that a function named f will be used in the function, and its return type and parameters are int.

| 陈述 | 定义 |
| --- | --- |
| 一个变量或函数可以被声明任意多次 | 一个变量或函数只能被定义一次 |
| 声明时，不会分配内存 | 定义时，会分配内存 |

```cpp
int f(int a)
{
  return a;
}
```

系统通过看到上面的函数定义来分配内存。