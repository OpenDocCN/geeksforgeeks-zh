# c++ 中的 alignof 运算符

> 原文:[https://www.geeksforgeeks.org/alignof-operator-in-c/](https://www.geeksforgeeks.org/alignof-operator-in-c/)

在 C++ 11 中，用于返回对齐方式的运算符的**对齐方式，以指定类型的字节为单位。
**语法:****

```cpp
alignof(type)
```

语法解释:

*   **alignoff:**运算符返回类型实例所需的字节对齐方式，类型可以是完整类型、数组类型或引用类型。
*   **数组类型:**返回元素类型的对齐要求。
*   **引用类型:**运算符返回引用类型的对齐方式。

**返回值:**alignof 运算符通常用于返回类型为 **std::size_t** 的值。

**程序:**

```cpp
// C++ program to demonstrate alignof operator
#include <iostream>
using namespace std;

struct Geeks {
    int i;
    float f;
    char s;
};

struct Empty {
};

// driver code
int main()
{
    cout << "Alignment of char: " << alignof(char) << endl;
    cout << "Alignment of pointer: " << alignof(int*) << endl;
    cout << "Alignment of float: " << alignof(float) << endl;
    cout << "Alignment of class Geeks: " << alignof(Geeks) << endl;
    cout << "Alignment of Empty class: " << alignof(Empty) << endl;

    return 0;
}
```

**Output:**

```cpp
Alignment of char: 1
Alignment of pointer: 8
Alignment of float: 4
Alignment of class Geeks: 4
Alignment of Empty class: 1

```

**alignof vs sizeof:**
**alignof**值与基本类型的 sizeof 值相同。考虑这个例子:

```cpp
typedef struct { int a; double b; } S;  
// alignof(S) == 8  

```

上述情况下，值的**对齐是结构中最大元素的对齐要求。
**演示 alignof 和 sizeof 区别的示例程序:****

```cpp
// C++ program to demonstrate
// alignof vs sizeof operator
#include <iostream>
using namespace std;

struct Geeks {
    int i;
    float f;
    char s;
};

int main()
{

    cout << "alignment of Geeks : " << alignof(Geeks) << '\n';
    cout << "sizeof of Geeks : " << sizeof(Geeks) << '\n';
    cout << "alignment of int : " << alignof(int) << '\n';
    cout << "sizeof of int     : " << sizeof(int) << '\n';
}
```

**Output:**

```cpp
alignment of Geeks : 4
sizeof of Geeks : 12
alignment of int : 4
sizeof of int     : 4

```