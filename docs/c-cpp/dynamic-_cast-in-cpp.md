# c++ 中的 Dynamic _ Cast

> 原文:[https://www.geeksforgeeks.org/dynamic-_cast-in-cpp/](https://www.geeksforgeeks.org/dynamic-_cast-in-cpp/)

[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 是一门功能强大的语言。在 C++ 中，我们可以编写一个结构化程序，也可以编写[面向对象程序](https://www.geeksforgeeks.org/oops-object-oriented-design/)。在本文中，我们将关注 C++ 中的**动态 _cast** 。现在在 C++ 中开始 dynamic_cast 之前，先了解一下什么是 C++ 中的[型铸造](https://www.geeksforgeeks.org/type-conversion-in-c/)。'

### [<u>型铸造</u>](https://www.geeksforgeeks.org/type-conversion-c/) :

转换是一种将一种数据类型转换为另一种数据类型的技术。用于此目的的操作员称为**演职人员**。它是一个**一元运算符**，强制将一种数据类型转换为另一种数据类型。它采用以下格式:

**语法:**

> (强制转换类型)表达式；
> 或
> 演员表类型(表达式)

**程序 1:**

## C++

```cpp
// C++ program to demonstrate the use
// of typecasting
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Variable declaration
    int a, b;
    float c;

    a = 20;
    b = 40;

    // Typecasting
    c = (float)a * b;

    cout << "Result: " << c;

    return 0;
}
```

**Output:**

```cpp
Result: 800

```

**说明:**在上面的例子中，首先将变量 **a** 转换为 **float** 然后乘以 **b** ，现在结果也是 floating float 然后将结果赋给变量 **c** 。现在 **c** 的数值是 **800** 。

**程序 2:**

## C++

```cpp
// C++ program to read the values of two
// variables and stored the result in
// third one
#include <iostream>
using namespace std;

int main()
{
    // Variable declaration and
    // initialization
    int a = 7, b = 2;
    float c;
    c = a / b;

    cout << "Result:" << c;

    return 0;
}
```

**Output:**

```cpp
Result:3

```

**说明:**在上述情况下，变量 **c** 是 **3** ，而不是 **3.5** ，因为变量 **a** 和 **b** 都是整数类型，所以 **a/b** 也是整数类型。计算后 **a/b** 即 **int** 类型被赋给变量 **c** 即 **float** 类型。但 **a/b** 是 **int** 型即 **7/2** 是 **3** ，不是 **3.5** 。因此，变量 **c** 的值为 **3** 。

**程序 3:**

## C++

```cpp
// C++ program to read two variable value
// (a, b) and perform typecasting
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Variable declaration and
    // initialization
    int a = 7, b = 2;
    float c;

    // Type Casting
    c = (float)a / b;
    cout << "Result :" << c;

    return 0;
}
```

**Output:**

```cpp
Result :3.5

```