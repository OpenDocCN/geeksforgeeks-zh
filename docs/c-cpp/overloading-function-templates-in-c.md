# c++ 中重载函数模板

> 原文:[https://www . geesforgeks . org/overloading-function-templates-in-c/](https://www.geeksforgeeks.org/overloading-function-templates-in-c/)

**模板:**

*   一个[模板](https://www.geeksforgeeks.org/templates-cpp/)是一个工具，它减少了编写相同代码的工作量，因为模板可以在那些地方使用。
*   模板函数可以被[非模板](https://www.geeksforgeeks.org/templates-cpp/)函数或者使用普通的函数模板重载。

**<u>函数重载</u> :** 在[函数重载](https://www.geeksforgeeks.org/function-overloading-c/)中，函数可能有相同的定义，但参数不同。下面是 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)来说明函数重载:

## C++

```cpp
// C++ program to demonstrate the
// function overloading
#include <bits/stdc++.h>
using namespace std;

// Function to calculate square
void square(int a)
{
    cout << "Square of " << a
         << " is " << a * a
         << endl;
}

// Function to calculate square
void square(double a)
{
    cout << "Square of " << a
         << " is " << a * a
         << endl;
}

// Driver Code
int main()
{
    // Function Call for side as
    // 9 i.e., integer
    square(9);

    // Function Call for side as
    // 2.25 i.e., double
    square(2.25);
    return 0;
}
```

**Output:**

```cpp
Square of 9 is 81
Square of 2.25 is 5.0625

```

**说明:**

*   在上面的代码中，**方块**重载了不同的参数。
*   函数 **square** 也可以重载其他参数，每次都需要相同的名称和不同的参数。
*   为了减少这些努力， [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 引入了一个名为**函数模板**的泛型类型。

**<u>函数模板</u> :** 函数模板的语法与常规函数相同，但它以一个[关键字](https://www.geeksforgeeks.org/cc-tokens/) **模板**开始，后面是包含在**角括号< >内的模板参数。**

> 模板<class t=""></class>
> 
> 测试函数名(测试参数)
> {
> //函数定义
> ……。…… …..…….
> }
> 其中， **T** 是**模板**论点接受不同论点，**类**是关键词。

**模板函数重载:**

*   函数模板名称相同但调用参数不同的称为**函数模板重载**。
*   如果函数模板与普通模板相同，函数的名称保持不变，但参数的数量不同。
*   当函数模板被非模板函数重载时，函数名保持不变，但函数的参数不同。

下面是使用显式函数说明模板函数重载的程序:

## C++

```cpp
// C++ program to illustrate overloading
// of template function using an
// explicit function
#include <bits/stdc++.h>
using namespace std;

// Template declaration
template <class T>

// Template overloading of function
void display(T t1)
{
    cout << "Displaying Template: "
         << t1 << "\n";
}

// Template overloading of function
void display(int t1)
{
    cout << "Explicitly display: "
         << t1 << "\n";
}

// Driver Code
int main()
{
    // Function Call with a
    // different arguments
    display(200);
    display(12.40);
    display('G');

    return 0;
}
```

**Output:**

```cpp
Explicitly display: 200
Displaying Template: 12.4
Displaying Template: G

```