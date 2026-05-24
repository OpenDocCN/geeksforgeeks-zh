# 如何声明函数的指针？

> 原文:[https://www . geesforgeks . org/如何声明指向函数的指针/](https://www.geeksforgeeks.org/how-to-declare-a-pointer-to-a-function/)

我们假设你知道 C 语言中的指针是什么意思，那么我们如何在 C 语言中创建一个指向整数的指针呢？嗯..这很简单..

```cpp
int * ptrInteger; /*We have put a * operator between int 
                    and ptrInteger to create a pointer.*/

```

这里 ptrInteger 是一个指向整数的指针。如果你明白这一点，那么从逻辑上讲，我们在声明一个指向函数的指针时应该不会有任何问题🙂

让我们先看看..我们如何声明一个函数？例如，

```cpp
int foo(int);

```

这里 foo 是一个返回 int 并接受 int 类型的一个参数的函数。所以作为一个逻辑学家会认为，通过在 int 和 foo(int)之间放一个*运算符应该创建一个指向函数的指针，即

```cpp
int * foo(int);

```

但是哎呀..c 运算符优先级在这里也起作用..所以在这种情况下，operator()将优先于 operator *。上面的声明意味着-一个函数 foo，它有一个 int 类型的参数，返回值为 int *即整数指针。所以它做了一些我们不想做的事情。🙁

因此，作为下一个逻辑步骤，我们必须以某种方式将运算符*与 foo 绑定。为此，我们将使用()运算符更改 C 运算符的默认优先级。

```cpp
int (*foo)(int);

```

就这样。这里* operator 是带有 foo 的，foo 是一个函数名。它做了我们想做的同样的事情。

所以这并没有我们之前想的那么难！