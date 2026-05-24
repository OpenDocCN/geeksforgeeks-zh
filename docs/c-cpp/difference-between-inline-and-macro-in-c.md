# c++ 中内联和宏的区别

> 原文:[https://www . geeksforgeeks . org/in-c 内联宏与宏的区别/](https://www.geeksforgeeks.org/difference-between-inline-and-macro-in-c/)

**1。内联:**
内联函数是由**内联**关键字定义的普通函数。内联函数是由编译器扩展的短函数。它的参数只计算一次。内联函数是短长度函数，在类内不使用**内联**关键字，自动成为内联函数。

**内联函数的语法:**

```cpp
inline return_type function_name ( parameters )
{ 
 // inline function code
}

```

**内联函数示例:**

```cpp
#include <iostream>
using namespace std;

// Inline function
inline int Maximum(int a, int b)
{
    return (a > b) ? a : b;
}

// Main function for the program
int main()
{
    cout << "Max (100, 1000):" << Maximum(100, 1000) << endl;
    cout << "Max (20, 0): " << Maximum(20, 0) << endl;

    return 0;
}
```

**输出:**

```cpp
Max (100, 1000): 1000
Max (20, 0): 20 
```

**2。宏:**
也叫**预处理器指令**。宏由 **#define** 关键字定义。在程序编译之前，只要预处理器检测到宏，预处理器就检查程序，然后预处理器用宏定义替换宏。

**宏语法:**

```cpp
#define MACRO_NAME Macro_definition 
```

**宏示例:**

```cpp
#include <iostream>
using namespace std;

// macro with parameter
#define MAXIMUM(a, b) (a > b) ? a : b

// Main function for the program
int main()
{
    cout << "Max (100, 1000):";
    int k = MAXIMUM(100, 1000);
    cout << k << endl;

    cout << "Max (20, 0):";
    int k1 = MAXIMUM(20, 0);
    cout << k1;

    return 0;
}
```

**输出:**

```cpp
Max (100, 1000):1000
Max (20, 0):20 
```

**c++ 中内联和宏的区别:**

| S.NO | 在一条直线上的 | 宏指令 |
| --- | --- | --- |
| 1. | 内联函数由**内联**关键字定义。 | 而宏是由 **#define** 关键字定义的。 |
| 2. | 通过内联函数，可以访问类的数据成员。 | 而宏不能访问类的数据成员。 |
| 3. | 在内联函数的情况下，程序很容易调试。 | 而在宏的情况下，程序不容易调试。 |
| 4. | 在内联的情况下，参数只计算一次。 | 而在宏的情况下，每次在程序中使用宏时都会计算参数。 |
| 5. | 在 C++ 中，内联可以在类内定义，也可以在类外定义。 | 而宏始终是在程序开始时定义的。 |
| 6. | 在 C++ 中，在类内部，短长度函数自动成为内联函数。 | 而宏是专门定义的。 |
| 7. | 内联不如宏广泛使用。 | 而宏被广泛使用。 |
| 8. | 在竞争性编程中不使用内联。 | 而宏在竞争性编程中被大量使用。 |
| 9. | 内联函数由结尾的大括号终止。 | 虽然宏没有被任何符号终止，但是它被一个新的行终止。 |