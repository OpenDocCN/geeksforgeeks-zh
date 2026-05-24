# c++ 14 中的广义 Lambda 表达式

> 原文:[https://www . geesforgeks . org/generalized-lambda-expressions-C14/](https://www.geeksforgeeks.org/generalized-lambda-expressions-c14/)

在 C++ 11 中引入了 Lambda 表达式。它们基本上是代码片段，可以嵌套在其他函数甚至函数调用语句中。通过将 lambda 表达式与 auto 关键字相结合，这些表达式随后可以在程序中使用。

我们在这篇文章[中详细讨论了λ表达式。在继续阅读本文之前，请确保您已经阅读了链接的文章，或者了解 lambda 表达式语义，如范围捕获、返回值。](https://www.geeksforgeeks.org/lambda-expression-in-c/)

C++ 14 通过引入所谓的广义λ进一步完善了λ表达式。为了理解这个特性，让我们举一个普通的例子。假设我们创建一个 lambda 函数来返回两个整数之和。所以我们的λ函数看起来像

```cpp
[](int a, int b) -> int { return a + b; }

```

但是如果我们需要在以后获得两个**浮点**值的和呢。所以我们需要声明另一个 lambda 表达式，它只适用于双精度值。类似地，每次我们的输入参数类型改变时，lambda 函数都需要重写。

```cpp
[](double a, double b) -> double { return a + b; }

```

在 C++ 14 之前，有一种方法可以通过使用模板参数来避免这个问题，

```cpp
template<typename T>
[](T a, T b) -> T { return a + b };

```

C++ 14 取消了这一点，允许我们在 lambda 表达式的输入参数中使用关键字 *auto* 。因此，编译器现在可以在编译时推导出参数的类型。因此，在我们前面的例子中，一个适用于整数值和浮点值的 lambda 表达式将是

```cpp
[](auto a, auto b) { return a + b; }

```

这个特性的一个非常重要的应用是大大增强了现有的算法。以 [sort()](https://www.geeksforgeeks.org/sort-c-stl/) 功能为例。以下代码片段将按降序对所有数据类型进行排序(前提是它们已经重载了<运算符)。

```cpp
sort(container.begin(), container.end(), 
[](auto i, auto j) -> bool { return i > j; }

```

**这里有几个使用广义 lambdas 的示例程序:**

**例 1**

```cpp
// Cpp program to demonstrate
// generalized lambda expressions
#include <iostream>
#include <string>

using namespace std;
int main()
{

    // Declare a generalized lambda and store it in sum
    auto sum = [](auto a, auto b) {
        return a + b;
    };

    // Find sum of two integers
    cout << sum(1, 6) << endl;

    // Find sum of two floating numbers
    cout << sum(1.0, 5.6) << endl;

    // Find sum of two strings
    cout << sum(string("Geeks"), string("ForGeeks")) << endl;

    return 0;
}
```

**输出:**

```cpp
7
6.6
GeeksForGeeks

```

**例 2 :**

```cpp
// Cpp program to demonstrate
// how to sort integers, floats, strings
// floating data types using a 
// generalized lambda and sort function

#include <algorithm>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

// Utility Function to print the elements of a collection
void printElements(auto& C)
{

    for (auto e : C)
        cout << e << " ";

    cout << endl;
}

int main()
{

    // Declare a generalized lambda and store it in greater
    auto greater = [](auto a, auto b) -> bool {
        return a > b;
    };

    // Initialize a vector of integers
    vector<int> vi = { 1, 4, 2, 1, 6, 62, 636 };

    // Initialize a vector of doubles
    vector<double> vd = { 4.62, 161.3, 62.26, 13.4, 235.5 };

    // Initialize a vector of strings
    vector<string> vs = { "Tom", "Harry", "Ram", "Shyam" };

    // Sort integers
    sort(vi.begin(), vi.end(), greater);

    // Sort doubles
    sort(vd.begin(), vd.end(), greater);

    // Sort strings
    sort(vs.begin(), vs.end(), greater);

    printElements(vi);
    printElements(vd);
    printElements(vs);

    return 0;
}
```

**输出:**

```cpp
636 62 6 4 2 1 1
235.5 161.3 62.26 13.4 4.62                                                                         
Tom Shyam Ram Harry  

```

**注意:**广义 Lambda 表达式仅适用于 C++ 标准 14 及更高版本。支持 C++ 14 的编译器列表在参考资料部分给出

**参考文献:**

*   [https://isocpp . org/wiki/FAQ/CPP 14 语言](https://isocpp.org/wiki/faq/cpp14-language)