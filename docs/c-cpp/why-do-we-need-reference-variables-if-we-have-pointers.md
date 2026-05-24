# 如果有指针

为什么需要引用变量

> 原文:[https://www . geesforgeks . org/为什么我们需要引用变量如果我们有指针/](https://www.geeksforgeeks.org/why-do-we-need-reference-variables-if-we-have-pointers/)

[**指针**](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) **:** 指针是保存另一个变量内存地址的变量。指针需要用 ***** 操作符去引用才能访问它所指向的存储位置。
[**引用**](https://www.geeksforgeeks.org/references-in-c/) **:** 一个引用可以作为一个常量指针被调用，变成隐式去引用。当我们访问引用时，这意味着我们正在访问存储。
**既然有指针，为什么还要引用变量？**
在指针中要访问实际变量的值，我们需要通过在地址使用“**值”和“解引用运算符 **(*)** ”来显式地解引用指针变量。
在 References 中要访问实际变量的值，我们不需要显式取消引用引用变量，它们会自动被取消引用。
**指针和引用是等价的，除了:****

*   引用就像地址的**常量名**。我们需要在声明期间**初始化引用。一旦建立了对一个变量的引用，我们就不能改变引用来引用另一个变量。**
*   要获取指针指向的值**，我们需要使用**解引用**运算符 **(*)** 。**

> **例如:**如果 **a** 是整数类型的指针， ***a** 返回 **a** 指向的值。
> 要将变量 **b** 的地址分配到指针中，我们需要使用运算符 **( & )** 的地址。
> 例如:**int * a =&b .**T16】

*   引用用于将**置于指针**之上，以避免 [**对象切片**](https://www.geeksforgeeks.org/object-slicing-in-c/) 。

> [对象切片](https://www.geeksforgeeks.org/object-slicing-in-c/)当一个**派生类对象**被分配给一个**基类对象**时，派生类对象的附加属性被**切掉**形成基类对象。

*   在引用中，**引用**和**去引用**是通过**隐式**完成的。没有明确的去引用操作符 **(*)** 和将变量的地址分配给引用变量，没有操作符的地址(&)。
*   参考变量为**现有变量**提供了一个**新名称**。它是隐式去引用的，不需要去引用运算符 **(*)** 来检索引用的值。**鉴于**，要检索指针指向的**值** **，我们需要去引用操作符 **(*)** ，也就是所谓的**显式去引用**。**
*   引用可以被视为一个**常量指针**。在申报时必须是**初始化，不能更改内容。**

下面是指针和引用的说明程序:

## C++ 14

```cpp
// C++ program to illustrate
// pointer and references

#include <iostream>
using namespace std;

// function to illustrate
// pointer and references
void pointer_vs_reference()
{
    int num1 = 20, num2 = 23;

    // Pointer pointing to num1
    // Explicit referencing
    int* ptr1 = &num1;
    cout << *ptr1 << endl; // 20

    // Explicit dereferencing
    *ptr1 = 26;
    cout << *ptr1 << endl; // 26

    // pointer can be reassigned to
    // store another address
    ptr1 = &num2;
    cout << *ptr1 << endl; // 23

    // Reference to num1
    // Implicit referencing
    int& ref1 = num1;
    cout << ref1 << endl; // 26 not 20

    // Implicit dereferencing
    ref1 = 18;

    cout << ref1 << endl; // 18

    // reference cannot be reassigned
}

// Driver code
int main()
{
    pointer_vs_reference();
    return 0;
}
```

**Output:** 

```cpp
20
26
23
26
18
```

**输出说明:**

*   当指针 **ptr** 指向 **num1** var 时，它会打印 **20**
*   当 ***ptr** 被取消引用并更改值时，它会打印 **26**
*   类似于另一个名为 **num2 的变量，**打印 23
*   当参考 **ref1** 被 **num1** 初始化时，它打印的是 **26** 而不是 **20**
*   最后当 **18** 被分配到**参考文献 1** 中时，由于隐式去引用，它会打印 18

**参考变量说明:**
参考变量最好的例子是 [**复制构造函数**](https://www.geeksforgeeks.org/copy-constructor-in-cpp/) **的概念。**复制构造函数以一个**引用变量**为参数，这里不能使用指针。

## C++

```cpp
#include <iostream>
using namespace std;

class complex {
private:
    int a, b;

public:
    // Parametric constructor
    complex(int x, int y)
    {
        a = x;
        b = y;
    }
    // Copy constructor
    complex(const complex& c)
    {
        a = c.a;
        b = c.b;
    }

    // Function to print data
    void printData()
    {
        cout << "a = " << a << endl;
        cout << "b = " << b;
    }
};

int main()
{

    complex c1(5, 10);
    complex c2(c1);
    c2.printData();
}
```

**Output:** 

```cpp
a = 5
b = 10
```

**说明:**在上面的例子中，如果我们在复制构造函数的参数中取**指针**，那么复杂类的**对象将被一次又一次地创建**而永远不会被停止，这是**在 oops** 概念中的错误。**选择参照**只是这种情况下的解决方案。****