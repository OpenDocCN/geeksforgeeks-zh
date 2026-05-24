# 重载逗号运算符

> 原文:[https://www . geesforgeks . org/overloading-the-逗号运算符/](https://www.geeksforgeeks.org/overloading-the-comma-operator/)

在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，我们可以使用 [**运算符重载**](https://www.geeksforgeeks.org/operator-overloading-c/) 来重载[逗号运算符](https://www.geeksforgeeks.org/comna-in-c-and-c/)。**例如:**对于“*将查询 X 发送到服务器 Y 并将结果放入变量 Z”*，则*、*起逗号的作用。逗号运算符**(，)**用于隔离两个或多个表达式，这些表达式只包含一个表达式。当必须为操作数求解表达式集时，只考虑最右边的表达式。

**示例:**

> **输入:** x = (y = 5，y + 2)
> **输出:** x = 7，y = 5
> **解释:**
> 在上面的表达式中:
> 它会首先将值 5 赋给 y，然后将 y + 2 赋给变量 x。
> 因此，在末尾“x”会包含值 7，而变量“y”会包含值 7。

**抗过载操作员如下:**

*   [范围解析运算符(::)](https://www.geeksforgeeks.org/scope-resolution-operator-in-c/)
*   [sizeof()](https://www.geeksforgeeks.org/sizeof-operator-c/)
*   [成员选择器(。)](https://www.geeksforgeeks.org/dot-operator-in-c-c/)
*   成员指针选择器(*)
*   [三元运算符(？:)](https://www.geeksforgeeks.org/conditional-or-ternary-operator-in-c-c/)

**语法:**

> return _ type _ class _ name::operator op(argument _ list)
> {
> //body
> 
> }
> 
> 其中，
> 1) **return_type:** 是函数返回的值类型。
> 2) **班级 _ 名称:**是班级的名称。
> 3) **op:** 是一个运算符函数，其中 **op** 是被重载的运算符，运算符是关键字。

**操作员超载规则:**

*   现有运算符只能重载，但新运算符不能重载。
*   重载运算符至少包含一个用户定义数据类型的操作数。
*   friend 函数不能用来重载某些运算符。但是，成员函数可以用来重载这些运算符。
*   当一元运算符通过成员函数重载时，不采用显式参数，但是，如果它们被友元函数重载，则采用一个参数。
*   当二进制运算符通过成员函数重载时，需要一个显式参数，如果它们通过友元函数重载，则需要两个显式参数。

在下面的代码中，虽然每个表达式都由编译器计算，但是左侧表达式的值被丢弃。最后，右侧操作的值由函数返回。这将触发重载的逗号运算符以类似于其默认操作的方式运行。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// overloading the comma operator
#include <iostream>
using namespace std;

// Comma class
class comma {
    int x, y;

public:
    // Default Constructor
    comma() {}

    // Parameterized Constructor
    comma(int X, int Y)
    {
        x = X;
        y = Y;
    }

    // Function to display the value
    void display()
    {
        cout << "x=" << x << " ";
        cout << "y=" << y << " ";
    }

    comma operator+(comma ob2);
    comma operator, (comma ob2);
};

// Function to overload the + operator
comma comma::operator+(comma ob2)
{
    comma temp;

    // Update the value temp
    temp.x = ob2.x + x;
    temp.y = ob2.y + y;

    // Return the value temp
    return temp;
}

// Function to overload the, operator
comma comma::operator, (comma ob2)
{
    comma temp;

    // Update the value temp
    temp.x = ob2.x;
    temp.y = ob2.y;

    // Print the value
    cout << "x=" << ob2.x << " "
         << "y=" << ob2.y << endl;

    // Return the value temp
    return temp;
}

// Driver code
int main()
{
    // Initialize objects
    comma ob1(10, 20), ob2(5, 30), ob3(1, 1);

    ob1.display();
    ob2.display();
    ob3.display();

    cout << endl;

    ob1 = (ob2 + ob2, ob1, ob3);

    // Displays the value of
    // ob3 (Rightmost expression)
    ob1.display();

    return 0;
}
```

**Output:**

```cpp
x=10 y=20 x=5 y=30 x=1 y=1 
x=10 y=20
x=1 y=1
x=1 y=1

```

下面是另一个例子，在名为**坐标 3D** 的类中，**逗号(，**运算符被重载。

*   该类有 3 个内部隐藏变量 **x，y，z** 。
*   **Get()** 方法，是获取 **x，y，z** 值的访问方法。
*   操作符功能**操作符，()**，使操作符**“，”过载。**

下面是同样的程序:

## C++

```cpp
// C++ program to illustrate the
// overloading for comma operator

#include <iostream>
using namespace std;

// The class that defines the
// coordinates of a point in space
class Coords3D {

private:
    double x, y, z;

public:
    // Default Constructor
    Coords3D() { x = y = z = 0; }

    // Parameterized Constructor
    Coords3D(double x, double y,
             double z)
    {
        this->x = x;
        this->y = y;
        this->z = z;
    }

    // Function for updating the value
    // ofx, y, and z
    void Get(double& x, double& y,
             double& z)
    {
        x = this->x;
        y = this->y;
        z = this->z;
    }

    // Function to overloaded the
    // operator, (comma)
    Coords3D operator, (Coords3D obj)
    {
        Coords3D tmp;

        // Update the value of temp
        tmp.x = obj.x;
        tmp.y = obj.y;
        tmp.z = obj.z;

        // Return the value of temp
        return tmp;
    }
};

// Driver Code
int main()
{
    double x, y, z;

    // Instances of class Coords3D
    Coords3D c1(1, 3, 5);
    Coords3D c2(2, 4, 6);
    Coords3D c3;

    // Invoke the operator function
    // c3.operator, (c2) into c3
    // is saved c2
    c3 = (c1, c2);

    // Get the value of x, y, z
    c3.Get(x, y, z);

    // Print x, y, and z
    cout << "x = " << x << endl;
    cout << "y = " << y << endl;
    cout << "z = " << z << endl;

    // Create another instance
    Coords3D c4(10, 15, 20);

    // c3 <= c4
    c3 = (c2, c1, c4);

    // Checking
    // x = 10, y = 15, z = 20
    c3.Get(x, y, z);

    cout << endl;

    // Print x, y, and z
    cout << "x = " << x << endl;
    cout << "y = " << y << endl;
    cout << "z = " << z << endl;

    return 0;
}
```

**Output:**

```cpp
x = 2
y = 4
z = 6

x = 10
y = 15
z = 20

```