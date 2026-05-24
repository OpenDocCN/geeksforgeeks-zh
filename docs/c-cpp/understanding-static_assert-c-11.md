# 理解 C++ 11 中的 static _ assert

> 原文:[https://www . geesforgeks . org/understanding-static _ assert-c-11/](https://www.geeksforgeeks.org/understanding-static_assert-c-11/)

**什么是静态断言？**

静态断言是一种在编译代码时检查条件是否为真的方法。如果不是，编译器需要发出错误消息并停止编译过程。需要检查的条件是常量表达式。

*   执行编译时断言检查
*   语法:

```cpp
static_assert( constant_expression, string_literal ); 
```

**在 C++ 11 标准之前，静态断言是如何完成的？**

在 C++ 11 标准之前，产生编译时错误消息的主要方法是通过#error 指令，该指令使实现产生一个诊断消息，该消息包括跟随它的消息。例如:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Static assertion using #error directive
#include <iostream>
using namespace std;
#if !defined(__geeksforgeeks)
#error "Geeksforgeeks hasn't been defined yet".
#endif
int main()
{
    return 0;
}
```

**错误** : Geeksforgeeks 还没有定义。

**错误指令#有什么问题？**
这个#error 指令很好地将简单的任务。然而，当需要为复杂的任务进行编译时断言时，例如使用运算符的**大小检查数据类型的大小，它会失败。这是因为像“sizeof”这样的标记在预处理转换阶段之后才会转换为源标记，此时您不能再使用预处理指令。** 

**c++ 11 标准以来如何做静态断言？**

C++ 11 标准引入了一个名为 static_assert()的特性，可以用来在编译时测试软件断言。
**语法**:

```cpp
static_assert( constant_expression, string_literal ); 
Parameters:
constant_expression: An integral constant expression 
that can be converted to a Boolean.
string_literal: The error message that is displayed 
when the constant_expression parameter is false. 
```

“constant_expression”参数表示一个需要在编译时检查的软件断言(在程序的某个特定点上，这种情况应该是真的)。如果条件为真，static_assert 声明将无效。如果条件为假，断言失败，编译器在 string_literal 参数中显示消息，编译失败并出现错误。但是，需要注意的是，string_literal 参数是可选的。
**例**:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to demonstrate
// static assertion using static_assert
#include <iostream>
using namespace std;

template <class T, int Size>
class Vector {
    // Compile time assertion to check if
    // the size of the vector is greater than
    // 3 or not. If any vector is declared whose
    // size is less than 4, the assertion will fail
    static_assert(Size > 3, "Vector size is too small!");

    T m_values[Size];
};

int main()
{
    Vector<int, 4> four; // This will work
    Vector<short, 2> two; // This will fail

    return 0;
}
```

**输出**:

```cpp
error: static assertion failed: Vector size is too small!
```

在上面的代码中，我们创建了一个名为 vector 的模板类，我们不想创建一个小于 4 的向量。因此，在模板主体内部，我们放入一个 static_assert 语句来检查正在生成的向量的大小是否大于 3。如果失败，断言将失败，并显示错误消息:“向量大小太小”。
这正是在向量类对象‘二’的声明中发生的情况。传递给它的大小为“2”，这将导致无法检查条件，从而产生编译时错误，并因此停止编译过程。

**static _ assert 相比#error 有什么优势？**

*   与#error 不同，使用 static_assert 的断言发生在预处理转换阶段之后。因此，可以使用 static_assert 用 size of 检查数据类型的大小。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Datatype
#include <iostream>

using namespace std;
// No error produced.
// The program compiles well because
// the size of long datatype is 8 bytes
static_assert(sizeof(long) == 8,
ode relies on 'long' being exactly 8 bytes");
int main()
{
    return 0;
}
```

*   库可以在编译时检测常见的使用错误。
*   C++ 标准库的实现可以检测和诊断常见的使用错误，提高可用性。

**声明范围**
static_assert 可以用于命名空间范围、类范围以及块范围。上述每个范围的示例如下:

*   **命名空间范围:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// declaring static_assert in namespace scope
#include <iostream>
static_assert(sizeof(void*) == 8,
"DTAMDL(*LLP64) is not allowed for this module.");
int main()
{
    cout << "Assertion passed.
    The program didn't produce an error";
    return 0;
}
```

**输出**:

```cpp
assertion passed. The program didn't produce an error
```

*   **类范围:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate class scope in
// static assertion using static_assert
#include <iostream>
using namespace std;

template <class T, int Size>
class Vector {
    // Compile time assertion to check if
    // the size of the vector is greater than
    // 3 or not. If any vector is declared whose
    // size is less than 4, the assertion will fail
    static_assert(Size > 3, "Vector size is too small!");

    T m_values[Size];
};

int main()
{
    Vector<int, 4> four; // This will work
    Vector<short, 2> two; // This will fail

    return 0;
}
```

**输出**:

```cpp
error: static assertion failed: Vector size is too small!
```

*   **区块范围:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// declaring static_assert in block scope
template <typename T, int N>
void f()
{
    static_assert(N >= 0, "length of array a is negative.");
    T a[N];
}
int main()
{
    // assertion fails here
    // because the length of the array passed
    // is below 0
    f<int, -1>();
    return 0;
}
```

**输出:**

```cpp
error: static assertion failed: length of array a is negative.
```

**错误的 static _ assert**
static _ assert 中传递的常量 _ 表达式需要是有效的表达式。例如，考虑以下代码:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// demonstrating an erroneous static_assert declaration
int main()
{
    static_assert(1 / 0, "never shows up!");
    return 0;
}
```

输出:

```cpp
prog.cpp:5:2: error: non-constant condition for static assertion
  static_assert(1 / 0, "never shows up!");
  ^
```

在上面这段代码中，表达式“ **1/0** ”不是有效的常量表达式。因此，编译时，编译器不会在 static_assert 声明中显示字符串文字，而是发出一条错误消息，指示除数不能为零。