# 在 C++ 中将函数作为参数传递

> 原文:[https://www . geesforgeks . org/passing-a-function-as-a-parameter-in-CPP/](https://www.geeksforgeeks.org/passing-a-function-as-a-parameter-in-cpp/)

一个[函数](https://www.geeksforgeeks.org/functions-in-c/)是一组接受输入、执行一些特定计算并产生输出的语句。使用函数的想法是一起执行一些通常或重复完成的任务，并创建一个函数，这样就不用为不同的输入一次又一次地编写相同的代码。函数的一般形式是:

> **return _ type function _ name([arg 1 _ type arg 1 _ name，… ]) {**
> 
> **//执行操作**
> 
> **}**

传递函数作为[参数](https://www.geeksforgeeks.org/command-line-arguments-in-c-cpp/)在 [C/C++ ](https://www.geeksforgeeks.org/difference-between-c-and-c/) 中是一个有用的概念。在[**【STD::sort()**](https://www.geeksforgeeks.org/sort-c-stl/)**中传递自定义[比较器函数](https://www.geeksforgeeks.org/comparator-class-in-c-with-examples/)作为参数，根据需要对一系列[对象](https://www.geeksforgeeks.org/c-classes-and-objects/)进行排序时，已经使用了这个概念。在本文中，我们将讨论设计接受另一个函数作为参数的函数的不同方法。**

****<u>将</u>** [**<u>指针</u>**](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) **<u>转到一个功能</u> :****

**一个函数也可以通过将其地址传递给另一个函数来传递给该函数。下面是 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)来说明同样的情况:**

## **C++**

```cpp
// C++ program to pass function as a
// pointer to any function

#include <iostream>
using namespace std;

// Function that add two numbers
int add(int x, int y)
{
    return x + y;
}

// Function that multiplies two
// numbers
int multiply(int x, int y)
{
    return x * y;
}

// Function that takes a pointer
// to a function
int invoke(int x, int y,
           int (*func)(int, int))
{
    return func(x, y);
}

// Driver Code
int main()
{
    // Pass pointers to add & multiply
    // function as required
    cout << "Addition of 20 and 10 is ";
    cout << invoke(20, 10, &add)
         << '\n';

    cout << "Multiplication of 20"
         << " and 10 is ";
    cout << invoke(20, 10, &multiply)
         << '\n';

    return 0;
}
```

****Output:**

```cpp
Addition of 20 and 10 is 30
Multiplication of 20 and 10 is 200

```** 

****<u>使用 std::功能< ></u> :****

**在 [C++ 11](https://www.geeksforgeeks.org/c-11-vs-c-14-vs-c-17/) 中，有一个 std::function < > [模板](https://www.geeksforgeeks.org/templates-cpp/)类，允许将函数作为对象传递。std::function < > 的一个[对象可以如下创建。](https://www.geeksforgeeks.org/c-classes-and-objects/)**

> ****STD::function<return _ type(arg 1 _ type，arg 2-type……)>obj _ name****
> 
> **//这个对象可以用来调用如下函数**
> 
> ****return _ type catch _ variable = obj _ name(arg 1，arg 2)；****

**下面是说明将一个函数对象作为参数传递给另一个函数的程序:**

## **C++**

```cpp
// C++ program to illustrate the passing
// of functions as an object parameter
#include <functional>
#include <iostream>
using namespace std;

// Define add and multiply to
// return respective values
int add(int x, int y)
{
    return x + y;
}
int multiply(int x, int y)
{
    return x * y;
}

// Function that accepts an object of
// type std::function<> as a parameter
// as well
int invoke(int x, int y,
           function<int(int, int)> func)
{
    return func(x, y);
}

// Driver code
int main()
{
    // Pass the required function as
    // parameter using its name
    cout << "Addition of 20 and 10 is ";
    cout << invoke(20, 10, &add)
         << '\n';

    cout << "Multiplication of 20"
         << " and 10 is ";
    cout << invoke(20, 10, &multiply)
         << '\n';

    return 0;
}
```

****Output:**

```cpp
Addition of 20 and 10 is 30
Multiplication of 20 and 10 is 200

```** 

****<u>使用兰姆达斯</u> :****

**C++ 中的 [Lambdas](https://www.geeksforgeeks.org/lambda-expression-in-c/) 提供了一种定义内联、一次性、匿名函数对象的方法。这些 lambdas 可以在需要传递函数作为参数的地方定义。下面是 C++ 程序来说明同样的情况:**

## **C++**

```cpp
// C++ program to pass the function as
// parameter as a lambda expression
#include <functional>
#include <iostream>
using namespace std;

// Function that takes a pointer
// to a function
int invoke(int x, int y,
           function<int(int, int)> func)
{
    return func(x, y);
}

// Driver Code
int main()
{

    // Define lambdas for addition and
    // multiplication operation where
    // we want to pass another function
    // as a parameter

    // Perform Addition
    cout << "Addition of 20 and 10 is ";
    int k = invoke(20, 10,
                   [](int x,
                      int y) -> int {
                       return x + y;
                   });

    cout << k << '\n';

    // Perform Multiplication
    cout << "Multiplication of 20"
         << " and 10 is ";
    int l = invoke(20, 10,
                   [](int x,
                      int y) -> int {
                       return x * y;
                   });

    cout << l << '\n';

    return 0;
}
```

****Output:**

```cpp
Addition of 20 and 10 is 30
Multiplication of 20 and 10 is 200

```**