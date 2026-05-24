# 在 C++ 中重载下标或数组索引运算符[]

> 原文:[https://www . geesforgeks . org/overload-下标或数组-index-operator-in-c/](https://www.geeksforgeeks.org/overloading-subscript-or-array-index-operator-in-c/)

下标或数组索引运算符用“[]”表示。该运算符通常用于数组，以检索和操作数组元素。
这是一个二元或 n 元运算符，由两部分组成:

1.  后缀/主表达式
2.  表示

后缀表达式，也称为主表达式，是指针值，如数组或标识符，第二个表达式是整数值。在第二个表达式中，我们还可以包含枚举值。

**语法:**

```cpp
postfix-expression[expression];

Example: Ramswarup[10];
Here the Ramswarup is an array and the above
statement print the value which is held by
Ramswarup at index position 10.

```

下标操作符后面的主表达式是指针，它可以是整数值，但是必须记住，两个表达式中的一个表达式必须是指针值，第二个表达式是否是整数值并不重要。
**例:**

```cpp
// CPP program to demonstrate []
// operator
#include <iostream>
using namespace std;
int main()
{
    char name[] = "Ramswarup Tushar Nilesh Subhash";

    // Both of the statement prints same thing
    cout << name[5] << endl;
    cout << 5 [name] << endl;
    return 0;
}
```

**Output:**

```cpp
a
a

```

```cpp
OUTPUT
a
a

```

**解释:**
在上面的例子中，由于下标操作符的排他属性，两个“cout”语句都提供了类似的输出。编译器以类似的方式读取两个语句，因此 ***(名称+ 5)** 和 ***(5 +名称)**没有区别。

**正负下标**
数组的第一个元素存储在索引 0 处。C++ 数组的范围是从数组[0]到数组[大小–1]。但是，C++ 支持正下标和负下标。负数下标必须在数组边界内；如果他们不这样做，结果是不可预测的。下面的代码显示了正负数组下标:

```cpp
// CPP program illustrating the
// positive and negative subscripts
#include <iostream>
using namespace std;

// Driver Method
int main()
{
    int intArray[1024];
    for (int i = 0, j = 0; i < 1024; i++) {
        intArray[i] = j++ ;
    }

    // 512
    cout << intArray[512] << endl;

    // 257
    cout << 257 [intArray] << endl;

    // pointer to the middle of the array
    int* midArray = &intArray[512];

    // 256
    cout << midArray[-256] << endl;

    // unpredictable, may crash
    cout << intArray[-256] << endl;
}
```

**Output:**

```cpp
512
257
256
0

```

最后一行中的负下标会产生运行时错误，因为它指向一个地址-256 个位置，这些位置在内存中可能低于数组的原点。数组中的指针被初始化到数组的中间；因此，可以(但不建议)同时使用正数组索引和负数组索引。数组下标错误不会产生编译时错误，但它们可能会产生不可预测的结果。

我们引入了[操作符重载](https://www.geeksforgeeks.org/operator-overloading-c/)。本文讨论了索引运算符[]的重载。
以下是关于[]超载的一些有用事实。
1)当我们想要检查索引是否超出界限时，[]的重载可能会很有用。
2)我们必须在函数中通过引用返回，因为像“arr[i]”这样的表达式可以用作左值。

下面是演示数组索引运算符[]重载的 C++ 程序。

```cpp
// Overloading operators for Array class
#include <cstdlib>
#include <iostream>

using namespace std;

// A class to represent an integer array
class Array {
private:
    int* ptr;
    int size;

public:
    Array(int*, int);

    // Overloading [] operator to access elements in array style
    int& operator[](int);

    // Utility function to print contents
    void print() const;
};

// Implementation of [] operator.  This function must return a
// reference as array element can be put on left side
int& Array::operator[](int index)
{
    if (index >= size) {
        cout << "Array index out of bound, exiting";
        exit(0);
    }
    return ptr[index];
}

// constructor for array class
Array::Array(int* p = NULL, int s = 0)
{
    size = s;
    ptr = NULL;
    if (s != 0) {
        ptr = new int[s];
        for (int i = 0; i < s; i++)
            ptr[i] = p[i];
    }
}

void Array::print() const
{
    for (int i = 0; i < size; i++)
        cout << ptr[i] << " ";
    cout << endl;
}

// Driver program to test above methods
int main()
{
    int a[] = { 1, 2, 4, 5 };
    Array arr1(a, 4);
    arr1[2] = 6;
    arr1.print();
    arr1[8] = 6;
    return 0;
}
```

**Output:**

```cpp
1 2 6 5 
Array index out of bound, exiting

```

输出:

```cpp
1 2 6 5
Array index out of bound, exiting
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论