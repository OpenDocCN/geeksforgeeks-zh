# c++ 中的即时函数

> 原文:[https://www.geeksforgeeks.org/immediate-functions-in-cpp/](https://www.geeksforgeeks.org/immediate-functions-in-cpp/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中使用的立即函数。

**<u>即时功能</u> :**

*   在 C++ 20 中，立即[函数](https://www.geeksforgeeks.org/functions-in-c/)是这样一个函数，其中对该函数的每次调用都直接或间接产生一个编译时常数表达式。
*   这些函数在返回类型之前使用**常量** [关键字](https://www.geeksforgeeks.org/variables-and-keywords-in-c/)来声明。

下面给出了一些与即时功能相关的重要术语:

### **<u>常量表达式功能</u> :**

*   **constexpr** 说明符声明可以在编译时计算一个函数或变量的值。
*   这样的变量和函数可以在只允许[编译时常数](https://www.geeksforgeeks.org/runtime-and-compile-time-constants-in-c/)表达式的地方使用。
*   这些函数用于通过在编译时而不是运行时进行计算来提高程序的性能。
*   这些函数确实很有帮助，其中[多次执行一个程序](https://www.geeksforgeeks.org/how-does-a-c-program-executes/)，因为常量表达式在编译时只会被求值一次。

下面是 C++ 程序，演示了 constexpr 函数的使用:

## C++ 14

```cpp
// C++ program demonstrates the use of
// constexpr
#include <iostream>
using namespace std;

// Constexpr function if replaced with
// consteval, program works fine
constexpr int fib(int n)
{
    // Base Case
    if (n <= 1)
        return n;

    // Find the Fibonacci Number
    return fib(n - 1) + fib(n - 2);
}

// Driver Code
int main()
{
    // Constant expression evaluated
    // at compile time
    const int val = fib(22);

    cout << "The fibonacci number "
         << "is: " << val << "\n";

    return 0;
}
```

**Output**

```cpp
The fibonacci number is: 17711

```

**说明:**

*   在上例中， **fib()** 用 **22** 来调用。
*   这就是为什么，它是一个常量表达式，所以可以在[编译时](https://www.geeksforgeeks.org/difference-between-compile-time-errors-and-runtime-errors/)进行求值。
*   程序在使用**常量**或**常量**时都没有显示错误。
*   但是，如果在使用 consteval 关键字时使用常量表达式，程序将会产生错误。

### **<u>常量功能</u> :**

*   在**常量**函数中，对该函数的每次调用都必须直接或间接产生一个[编译时常量表达式](https://www.geeksforgeeks.org/runtime-and-compile-time-constants-in-c/)。
*   consteval 函数与 constexpr 函数相同，只是如果对 consteval 函数的调用没有计算为编译时常量表达式，则程序会给出一个错误，而在 [**constexpr** 函数](https://www.geeksforgeeks.org/understanding-constexper-specifier-in-c/)的情况下则不是这样。
*   **常量表达式**指定变量或函数的值可以出现在常量表达式中。
*   这里要注意的关键是，它说，一个函数可以出现在常量表达式中，它并没有说函数必须是，而一个 **consteval** 则指定一个函数是立即函数，也就是说，对该函数的每次调用都必须产生一个编译时常量。

下面是演示 consteval 函数使用的 C++ 程序:

## C++ 14

```cpp
// C++ program illustrating the use
// of the consteval function

#include <iostream>
using namespace std;

// If constexpr replaces with consteval
// program gives an error in C++ 20
constexpr int fib(int n)
{
    // Base Case
    if (n <= 1)
        return n;

    return fib(n - 1) + fib(n - 2);
}

// Driver Code
int main()
{
    // This expression is not evaluated
    // at compile time
    const int val = fib(rand() % 20);

    cout << "The fibonacci number is: "
         << val << "\n";

    return 0;
}
```

**Output**

```cpp
The fibonacci number is: 2

```

**说明:**

*   在上面的例子中，使用了 [**【兰德()】**](https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/) ，并且**兰德()**在运行时而不是编译时被求值，因此，表达式不再是常量表达式，这就是为什么我们的 **consteval** 函数现在会产生错误。
*   虽然 **constexpr 函数**仍然工作正常，原因是它不必在编译时运行。

**结论:**

*   从上面的讨论可以得出结论，立即函数是**常量函数**，只有当对该函数的每次调用都必须直接或间接产生编译时常量表达式，否则会产生错误时，该函数才能正常工作。
*   这些函数在其返回类型之前使用 consteval 关键字声明，用于减少计算常量表达式所消耗的时间，因为它们在编译时只计算常量表达式一次，而不是在程序的每次[运行/执行](https://www.geeksforgeeks.org/how-does-a-c-program-executes/)期间。
*   因此，当需要多次执行带有一些常量表达式的程序时，它节省了大量的时间。