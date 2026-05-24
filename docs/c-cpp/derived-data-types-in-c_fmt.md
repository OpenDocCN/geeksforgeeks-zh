# C++ 中的派生数据类型

> 原文: [https://www.geeksforgeeks.org/derived-data-types-in-c/](https://www.geeksforgeeks.org/derived-data-types-in-c/)

**数据类型**是识别数据类型和处理数据的相关操作的手段。有三种数据类型:

1.  [预定义数据类型](https://www.geeksforgeeks.org/c-data-types/)
2.  派生数据类型
3.  [用户定义的数据类型](https://www.geeksforgeeks.org/user-defined-derived-data-types-in-c/)

[![](img/2dfd5a89edd11ae31b66eeecfeefef60.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191113121619/DatatypesInC1.png)
本文对派生数据类型进行了解释:

### 派生数据类型

从基元或内置数据类型派生的数据类型称为派生数据类型。这些可以是四种类型，即:

*   [函数](https://www.geeksforgeeks.org/functions-in-c/)
*   [数组](https://www.geeksforgeeks.org/arrays-in-c-cpp/)
*   [指针](https://www.geeksforgeeks.org/pointers-c-examples/)
*   [引用](https://www.geeksforgeeks.org/references-in-c/)

让我们简要了解以下每个派生数据类型:

#### Function

[Function:](https://www.geeksforgeeks.org/functions-in-c/) 函数是一段代码或程序片段，被定义来执行一个特定的、定义明确的任务。函数通常被定义为使用户免于为相同的输入一遍又一遍地编写相同的代码行。所有的代码行都被放在一个函数中，可以在需要的地方调用。`main()` 是一个默认函数，在每个 C++ 程序中都有定义。

**语法:**

```
FunctionType FunctionName(parameters)
```

**示例:**

```cpp
// C++ program to demonstrate
// Function Derived Type

#include <iostream>
using namespace std;

// max here is a function derived type
int max(int x, int y)
{
    if (x > y)
        return x;
    else
        return y;
}

// main is the default function derived type
int main()
{
    int a = 10, b = 20;

    // Calling above function to
    // find max of 'a' and 'b'
    int m = max(a, b);

    cout << "m is " << m;
    return 0;
}
```

**Output:**

```
m is 20
```

#### Array

[Array:](https://www.geeksforgeeks.org/arrays-in-c-cpp/) 数组是存储在连续内存位置中的一组项目。数组的思想是在一个变量中表示多个实例。
![](img/a40fe60947982ce22d21c5a5bd91da41.png)

**语法:**

```
DataType ArrayName[size_of_array];
```

**示例:**

```cpp
// C++ program to demonstrate
// Array Derived Type

#include <iostream>
using namespace std;
int main()
{

    // Array Derived Type
    int arr[5];
    arr[0] = 5;
    arr[2] = -10;

    // this is same as arr[1] = 2
    arr[3 / 2] = 2;

    arr[3] = arr[0];

    cout<<arr[0]<<" "<<arr[1]<<" "<<arr[2]<<" "<<arr[3];

    return 0;
}
```

**Output:**

```
5 2 -10 5
```

#### Pointers

[Pointers:](https://www.geeksforgeeks.org/pointers-c-examples/) 指针是地址的符号表示。它们使程序能够模拟按引用调用，并创建和操作动态数据结构。它在 C/C++ 中的通用声明格式为：

**语法:**

```
datatype *var_name;
```

**示例:**

```cpp
int *ptr;

ptr points to an address
which holds int data
```

**示例:**

```cpp
// C++ program to illustrate
// Pointers Derived Type

#include <bits/stdc++.h>
using namespace std;

void geeks()
{
    int var = 20;

    // Pointers Derived Type
    // declare pointer variable
    int* ptr;

    // note that data type of ptr
    // and var must be same
    ptr = &var;

    // assign the address of a variable
    // to a pointer
    cout << "Value at ptr = "
         << ptr << "\n";
    cout << "Value at var = "
         << var << "\n";
    cout << "Value at *ptr = "
         << *ptr << "\n";
}

// Driver program
int main()
{
    geeks();
}
```

**Output:**

```
Value at ptr = 0x7ffc10d7fd5c
Value at var = 20
Value at *ptr = 20
```

#### Reference

[Reference:](https://www.geeksforgeeks.org/references-in-c/) 当一个变量被声明为引用时，它就成为了现有变量的别名。可以通过在声明中放入 `&` 来将变量声明为引用。

**示例:**

```cpp
// C++ program to illustrate
// Reference Derived Type

#include <iostream>
using namespace std;

int main()
{
    int x = 10;

    // Reference Derived Type
    // ref is a reference to x.
    int& ref = x;

    // Value of x is now changed to 20
    ref = 20;
    cout << "x = " << x << endl;

    // Value of x is now changed to 30
    x = 30;
    cout << "ref = " << ref << endl;

    return 0;
}
```

**Output:**

```
x = 20
ref = 30
```