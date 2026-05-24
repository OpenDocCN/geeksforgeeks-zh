# C 支持函数重载吗？

> 原文:[https://www . geesforgeks . org/dos-c-support-function-overloading/](https://www.geeksforgeeks.org/does-c-support-function-overloading/)

首先，什么是函数重载？函数重载是编程语言的一个特性，它允许一个程序有许多同名但不同签名的函数。
这个特性存在于大多数面向对象语言中，比如 C++ 和 Java。但是 C 不支持这个特性不是因为 OOP，而是因为编译器不支持(除了你可以使用 _Generic)。然而，人们可以间接地在 C 语言中实现类似的功能。其中一种方法如下。
有一个 void *类型的指针作为函数的参数。另一个参数告诉正在传递的第一个参数的实际数据类型。

```cpp
   int foo(void * arg1, int arg2);
```

假设，arg2 可以解释如下。0 = Struct1 类型变量，1 = Struct2 类型变量，等等。这里，结构 1 和结构 2 是用户定义的结构类型。
在不同的地方调用函数 foo 时……

```cpp
    foo(arg1, 0);   /*Here, arg1 is pointer to struct type Struct1 variable*/
    foo(arg1, 1);    /*Here, arg1 is pointer to struct type Struct2 variable*/
```

由于 foo 的第二个参数跟踪第一个类型的数据类型，因此在函数 foo 中，可以通过相应的类型转换获得第一个参数的实际数据类型。即在 foo 函数
内

## c

```cpp
if(arg2 == 0)
{
  struct1PtrVar = (Struct1 *)arg1;
}
else if(arg2 == 1)
{
  struct2PtrVar = (Struct2 *)arg1;
}
else
{
  /*Error Handling*/
}
```

在 C 语言中实现函数重载可以有其他几种方法，但是所有的方法都必须使用指针——C 语言最强大的功能
事实上，据说没有使用指针，就不能在现实世界的程序中有效地使用 C 语言&！
请注意，您可以使用“varargs”来实现这一点。