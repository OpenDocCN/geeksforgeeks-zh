# 在 C++ 中给变量赋值函数

> 原文:[https://www . geesforgeks . org/将函数分配给 cpp 中的变量/](https://www.geeksforgeeks.org/assigning-function-to-a-variable-in-cpp/)

在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，给[变量](https://www.geeksforgeeks.org/variables-and-keywords-in-c/)分配一个[函数](https://www.geeksforgeeks.org/functions-in-c/)，并根据用户需要多次使用该变量[调用函数](https://www.geeksforgeeks.org/what-happens-when-we-call-a-function/)，增加了代码的可重用性。下面是相同的语法:

**语法:**

## C++

```cpp
// Syntax:

// Below function is assigned to
// the variable fun
auto fun = [&]() {
    cout << "inside function"
         << " variable";
};
```

**程序 1:** 下面是实现分配给变量的函数的 C++ 程序:

## C++

```cpp
// C++ program to implement function
// assigned to a variable

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Below function i.e., is
    // assigned to the variable fun
    auto fun
        = [&]() {
              cout << "Inside Function Variable";
          };

    // Call the function using variable
    fun();

    return 0;
}
```

**Output**

```cpp
Inside Function Variable

```

**程序 2:** 下面是实现分配给变量的[参数化函数](https://www.geeksforgeeks.org/parameter-passing-techniques-in-c-cpp/)的 C++ 程序:

## C++

```cpp
// C++ program to implement parameterized
// function assigned to a variable
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Passing i and j as 2 parameters
    auto fun = [&](int i, int j) {
        cout << "Parameterised Function";
    };

    // Call the function using variable
    fun(4, 5);

    return 0;
}
```

**Output**

```cpp
Parameterised Function

```

**程序 3:** 下面是 C++ 程序，用于实现分配给变量的函数，该函数返回一个值:

## C++

```cpp
// C++ program to implement the function
// assigned to a variable returning
// some values
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Function taking 2 parameters
    // and returning sum
    auto sum = [&](int a, int b) {
        return a + b;
    };

    // Call the function using variables
    cout << "The sum is: "
         << sum(4, 5);

    return 0;
}
```

**Output**

```cpp
The sum is: 9

```