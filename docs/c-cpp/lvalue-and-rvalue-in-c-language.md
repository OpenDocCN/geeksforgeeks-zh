# C 语言中的左值和右值

> 原文:[https://www . geesforgeks . org/lvalue-and-rvalue-in-c 语言/](https://www.geeksforgeeks.org/lvalue-and-rvalue-in-c-language/)

**<u>L 值</u>:**“L 值”指的是识别一个对象的存储位置。l 值可能出现在赋值运算符(=)的左侧或右侧。l 值通常表示为标识符。

引用可修改位置的表达式称为“**可修改 l 值**”。可修改的 l 值不能有数组类型、不完整类型或带有**常量**属性的类型。对于可修改的结构和联合**左值**，它们不能有任何具有**常量**属性的成员。标识符的名称表示存储位置，而变量值是存储在该位置的值。

如果一个标识符引用一个存储单元，并且它的类型是算术、结构、并集或指针，那么它就是一个可修改的左值。例如，如果 ptr 是指向存储区域的指针，那么 ***ptr** 是可修改的 l 值，其指定 **ptr** 指向的存储区域。

在 C 语言中，这个概念被重新命名为**“定位器值”**，指的是定位(指定)对象的表达式。l 值是以下值之一:

1.  任何类型变量的名称，即整数、浮点、指针、结构或联合类型的标识符。
2.  不计算为数组的下标([ ])表达式。
3.  不引用数组的一元间接(*)表达式
4.  括号中的 l 值表达式。
5.  一个**常量**对象(一个不可修改的 l 值)。
6.  通过指针间接寻址的结果，前提是它不是函数指针。
7.  通过指针(->或)访问成员的结果。)

```cpp
// declare a an object of type 'int'
int a;

// a is an expression referring to an
// 'int' object as l-value
a = 1;

int b = a; // Ok, as l-value can appear on right

// Switch the operand around '=' operator
9 = a;

// Compilation error:
// as assignment is trying to change the
// value of assignment operator
```

**<u>R 值</u>** : r 值“是指存储在内存某个地址的数据值。r 值是不能赋值的表达式，这意味着 r 值可以出现在赋值运算符(=)的右侧，但不能出现在左侧。

```cpp
// declare a, b an object of type 'int'
int a = 1, b;

a + 1 = b; // Error, left expression is
           // is not variable(a + 1)

// declare pointer variable 'p', and 'q'
int *p, *q; // *p, *q are lvalue

*p = 1; // valid l-value assignment

// below is invalid - "p + 2" is not an l-value 
// p + 2 = 18; 

q = p + 5; // valid - "p + 5" is an r-value

// Below is valid - dereferencing pointer
// expression gives an l-value
*(p + 2) = 18;

p = &b; 

int arr[20]; // arr[12] is an lvalue; equivalent
              // to *(arr+12)
              // Note: arr itself is also an lvalue

struct S { int m; };

struct S obj; // obj and obj.m are lvalues

// ptr-> is an lvalue; equivalent to (*ptr).m
// Note: ptr and *ptr are also lvalues
struct S* ptr = &obj;
```

**注意**:一元&(的地址)运算符需要左值作为其操作数。也就是说，&只有当 n 是左值时，n 才是有效的表达式。因此，像& 12 这样的表述是错误的。同样，12 不引用对象，因此它是不可寻址的。例如，

```cpp
// declare a as int variable and
// 'p' as pointer variable
int a, *p;

p = &a; // ok, assignment of address
        // at l-value

&a = p;    // error: &a is an r-value

int x, y;

(  x < y ? y : x) = 0; // It's valid because the ternary
                  // expression preserves the "lvalue-ness"
                 // of both its possible return values
```

> 记住助记符，**左值**可以出现在赋值运算符的左侧，而**右值**可以出现在右侧

**参考:**T2[https://msdn.microsoft.com/en-us/library/bkbs2cds.aspx](https://msdn.microsoft.com/en-us/library/bkbs2cds.aspx)

本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。