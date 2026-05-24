# c++ 中重载子程序的调用和寻找精确匹配的方法

> 原文:[https://www . geeksforgeeks . org/调用重载子程序和方法来查找精确匹配的 c/](https://www.geeksforgeeks.org/calling-of-overloaded-subroutines-and-ways-for-finding-accurate-match-in-c/)

就像其他[子程序](https://www.geeksforgeeks.org/subroutine-subroutine-nesting-and-stack-memory/)一样，重载子程序也被调用。要决定调用哪个函数，确定参数的数量和类型很重要。例如，下面的代码部分将讲述调用重载子例程:

```cpp
prnsqr('z')                   // calls #2
prnsqr(13)                    // calls #1
prnsqr(134.520000012)         // calls #4
prnsqr(12.5F)                 // calls #3

```

当函数调用最初匹配可用的原型以及给定参数的数字和类型时，调用适当的[函数](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/)来执行。

在[浮点](https://www.geeksforgeeks.org/comparison-float-value-c/)值、双精度值或 [int](https://www.geeksforgeeks.org/int-1-sign-bit-31-data-bits-keyword-in-c/) 值或 [long](https://www.geeksforgeeks.org/need-long-data-type-c-cpp/) 值之间，可能会有歧义，如以下声明所调用的函数:

```cpp
void prnsqr(double d);
```

值为 1.24 时，可以假定为浮点或双精度。常量后缀(F、U、L、UL)等。这些值有助于演示要调用哪个重载子例程。普通的浮点常量(312.32)是双精度类型，F 后缀(312.32 F)是浮点类型，L (312.32 L)使其长双精度。对于整数，没有后缀的常数是 s [对齐的 int](https://www.geeksforgeeks.org/basics-of-signed-binary-numbers-of-ranges-of-different-datatypes/) 值。&u 后缀为无符号常量，L 后缀为长，LU 或 UL 为无符号长。这些后缀可以用小写字母或大写字母书写。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <iostream>
using namespace std;

class Distance {
private:
    int centimeter;
    int kilometer;

public:
    // Default Constructors
    Distance()
    {
        centimeter = 0;
        kilometer = 0;
    }

    // Parameterized Constructors
    Distance(int cm, int km)
    {
        centimeter = cm;
        kilometer = km;
    }

    // Overload function call
    Distance operator()(int a,
                        int b, int c)
    {
        Distance D;
        D.centimeter = a + c + 10;
        D.kilometer = b + c + 100;
        return D;
    }

    // To display distance
    void displayDistance()
    {
        cout << "centimeter: "
             << centimeter
             << "kilometer:"
             << kilometer << '\n';
    }
};

// Driver Code
int main()
{
    Distance D1(87, 33), D2;

    cout << "First Distance : ";
    D1.displayDistance();

    // Invoke operator()
    D2 = D1(10, 10, 10);
    cout << "Second Distance :";

    D2.displayDistance();

    return 0;
}
```

**Output:**

```cpp
First Distance : centimeter: 87kilometer:33
Second Distance :centimeter: 30kilometer:120

```

### 找到精确匹配的方法:

函数实例通过名为**参数匹配**的过程(也称为消歧过程)来解析重载子程序的调用。以下是可能导致函数调用的 3 种情况:

1.  **匹配:**找到函数调用。
2.  **不匹配:**为函数调用。
3.  **模糊匹配:**多个描述的实例匹配。

编译器将尝试为函数调用找到最佳匹配。

### <u>编译器为匹配</u>而采取的步骤

*   **Searching for an exact match:** When the actual argument type matches exactly with the type of one defined instance, the compiler will invoke for that instance. For Examples:

    ```cpp
    // For overloaded functions
    void afunc(int);
    void afunc(double);    

    // For exact match. Match afunc(int)
    afunc(0);

    ```

    0(零)是 int 类型，将 afunc(int)与 call 匹配。

    下面是同样的程序:

    ## C++

    ```cpp
    // C++ program for the above approach

    #include <iostream>
    using namespace std;

    // Function for integer parameter
    void afunc(int h)
    {
        cout << "Integer:" << h;
    }

    // Function for double parameter
    void afunc(double d)
    {
        cout << "double:" << d;
    }

    // Driver code
    int main()
    {
        afunc(0);
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Integer:0

    ```

*   **Match through promotion:** The compiler will make an attempt to get a match through the promotion of the actual argument if no exact match found. If all values cannot be represented by int and the conversion of integer types into (char, short, enumerator, int), or to unsigned int is called integral promotion. Now we will see the following code part:

    > 见 afunc(int)
    > 见 afunc(浮动)
    > 
    > //通过促销进行匹配
    > afunc('c ')
    > 
    > 其中，“c”是 char 类型，由于找不到完全匹配，被提升为 INT 类型。

    下面是同样的程序:

    ## C++

    ```cpp
    // C++ program for the above approach
    #include <iostream>
    using namespace std;

    // Function for integer parameter
    void value(int s)
    {
        cout << "Integer:" << s;
    }

    // Function for character parameter
    void value(char* b)
    {
        cout << "Char:" << b;
    }

    // Driver Code
    int main()
    {
        char st = 'd';
        value(st);
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Integer:100

    ```

*   **Through the application of the standard [C++ conversion rule](https://www.geeksforgeeks.org/type-conversion-in-c/) found a match:** An attempt is made to achieve a match through a standard conversion of the actual argument if no exact match or match through a promotion is found. Below is the example for the same:

    > see afunc(char)
    > see afunc(double)
    > 
    > //通过标准转换进行匹配
    > afunc(471)
    > 匹配一个 func(双精度)

    使用 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 标准转换规则，int 参数 **471** 可以转换为双精度值 **471** ，如果实际参数可以转换为多种形式参数类型，编译器将生成一条错误消息，因为它是不明确的匹配。例如:

    ```cpp
    void afunc(long)
    void afunc(double)

    // Error will generate as ambiguous match
    afunc(15)

    ```

    int 参数 15 被转换为 long 或 double，从而导致使用 afunc()的情况不明确。

    下面是同样的程序:

    ## C++

    ```cpp
    // C++ program to explain the standard
    // conversion rule
    #include <iostream>
    using namespace std;

    // Driver Code
    int main()
    {
        // integer h
        int h = 11;

        // character c
        char s = 'a';

        // s implicitly converted
        // to int. ASCII value of
        // 'a' is 97
        h = h + s;

        // h is implicitly converted
        // to float
        float f = h + 1.0;

        cout << "h = " << h << endl
             << "s = " << s << endl
             << "f = " << f << endl;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    h = 108
    s = a
    f = 109

    ```

    **注意:**如果没有看到升级，那么编译器通过标准转换找到匹配。任何数值类型都与另一个数值类型匹配，包括无符号(比如 int 和 float)。枚举将与数字类型的形式类型相匹配(例如，枚举为浮点型)。0 必须与指针类型和数字类型相匹配(比如 0 与 char*，0 与 float)。尽管指针与空指针匹配。

*   **Through the application of a user define conversion find a match:** Now the compiler will use a user-defined conversion in combination with integral promotion and built-in conversions to find a unique match if all the above steps will fail. Any function whether it is a class member or just a normal function can be overloaded in C++ given is needed to work for different argument types numbers and combinations.

    下面是同样的程序:

    ## C++

    ```cpp
    // C++ program to illustrate the user
    // defined type casting
    #include <iostream>
    using namespace std;

    // Driver Code
    int main()
    {
        double h = 1.4;

        // Explicit conversion
        // from double to int
        int add = (int)h + 2;

        cout << "Add = " << add;
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Add = 3

    ```