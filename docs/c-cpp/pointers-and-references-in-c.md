# c++ 中的指针和引用

> 原文:[https://www.geeksforgeeks.org/pointers-and-references-in-c/](https://www.geeksforgeeks.org/pointers-and-references-in-c/)

1.  [**c++ 中的指针:**](https://www.geeksforgeeks.org/pointers-c-examples/) 指针是地址的符号表示。它们使程序能够模拟按引用调用，以及创建和操作动态数据结构。它在 C/C++ 中的一般声明格式为:
    **语法:**

```cpp
datatype *var_name; 
```

1.  **例:**

```cpp
// ptr can point to an address
// which holds int data
int *ptr;   
```

2.  [**More on Pointers in C++ :**](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) This article would provide a further insight into Pointers, on how it works and explains the mathematical background of it. Pointers store address of variables or a memory location. 

```cpp
// General syntax
datatype *var_name; 

// An example pointer "ptr" that holds
// address of an integer variable or holds
// address of a memory whose value(s) can
// be accessed as integer values through "ptr"
int *ptr;
```

2.  [**指针在 C/C++ 中的应用:**](https://www.geeksforgeeks.org/applications-of-pointers-in-c-cpp/) 指针有多种应用，例如:
    *   通过引用传递参数:通过引用传递有两个目的
    *   对于访问数组元素:编译器在内部使用指针来访问数组元素。
    *   返回多个值:例如，返回平方和数字的平方根。
    *   动态内存分配:我们可以使用指针来动态分配内存。动态分配内存的好处是，在我们显式删除它之前，它不会被删除。
    *   实现数据结构。
    *   在内存地址有用的地方进行系统级编程。
3.  [**C/c++ 中指针的特性和使用:**](https://www.geeksforgeeks.org/features-and-use-of-pointers-in-c-c/) 指针几乎没有什么重要的特性，比如节省内存空间、用于动态分配内存、用于文件处理等。指针存储变量地址或存储位置。
    **语法:**

```cpp
datatype *var_name; 
```

1.  **Example:** pointer “ptr” holds the address of an integer variable or holds the address of memory whose value(s) can be accessed as integer values through “ptr” 

```cpp
int *ptr;
```

2.  [**【c++ 中的‘this’指针】**](https://www.geeksforgeeks.org/this-pointer-in-c/) 这个‘this’指针作为一个隐藏的参数传递给所有非静态成员函数调用，并且可以作为所有非静态函数体内的局部变量使用。“this”指针在静态成员函数中不可用，因为静态成员函数可以在没有任何对象(带有类名)的情况下调用。即使每个函数中只有一个成员被多个对象使用，编译器也会提供一个隐式指针以及函数名“this”。
    **申报:**

```cpp
this->x = x; 
```

2.  [**c++ 中的引用:**](https://www.geeksforgeeks.org/references-in-c/) 当一个变量被声明为引用时，它就变成了一个现有变量的替代名称。变量可以通过在声明中放入“&”来声明为引用。有 3 种方法可以将 C++ 参数传递给函数:
    *   按值调用
    *   带指针参数的按引用调用
    *   带有引用参数的引用调用
3.  [**c++ 中的指针与引用:**](https://www.geeksforgeeks.org/pointers-vs-references-cpp/) 本文为指针和引用之间的区别奠定了适当的基础。引用和指针都可以用来改变一个函数在另一个函数中的局部变量。当作为参数传递给函数或从函数返回时，这两种方法都可以用来节省大对象的复制，从而提高效率。
    尽管有上述相似之处，但引用和指针之间存在以下差异。
    *   A pointer can be declared as void but a reference can never be void 
        **Example:** 

```cpp
int a = 10;
void* aa = &a;. //it is valid
void &ar = a; // it is not valid
```

*   引用不如指针强大
*   一旦创建了引用，以后就不能再引用另一个对象；无法重新拔插。这通常是通过指针来完成的。
*   引用不能为空。指针通常为空，表示它们没有指向任何有效的东西。
*   声明引用时必须对其进行初始化。指针没有这样的限制

1.  [**C++ 中通过指针传递与通过引用传递:**](https://www.geeksforgeeks.org/passing-by-pointer-vs-passing-by-reference-in-c/) 在 c++ 中，我们可以通过指针或引用将参数传递给函数。在这两种情况下，我们得到相同的结果。那么应该选择什么，为什么？
2.  [**在 C++ 中传递对指针的引用:**](https://www.geeksforgeeks.org/passing-reference-to-a-pointer-in-c/) 在本文中，让我们比较“指针对指针”和“引用对指针”在某些情况下的用法。