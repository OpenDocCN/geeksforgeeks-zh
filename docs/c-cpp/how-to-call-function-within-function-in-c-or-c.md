# 如何在 C 或 C++ 中调用函数内的函数

> 原文:[https://www . geeksforgeeks . org/如何在 c-or-c/](https://www.geeksforgeeks.org/how-to-call-function-within-function-in-c-or-c/) 函数中调用函数

当我们开始用 C/C++ 编程时，我们通常编写一个 main()函数，并在其中编写我们所有的逻辑。这种方法适用于非常小的程序，但是随着程序规模的增长，这变得难以管理。所以我们使用[功能](https://www.geeksforgeeks.org/functions-in-c/)。我们以函数的形式编写代码。主函数总是充当驱动函数并调用其他函数。

```cpp
// C++ program to call a function in main
#include <iostream>
using namespace std;

// Function called inside main
int add(int num1, int num2)
{
    return (num1 + num2);
}

// Driver code
int main()
{
    int num1 = 12, num2 = 34;
    cout << add(num1, num2);
    return 0;
}
```

**Output:**

```cpp
46

```

我们也可以写函数调用作为函数的参数。在下面的代码中，首先计算 add(num1，num2)，让结果为 r1。计算 add(r1，num3)。假设结果是 r2。最后，计算 add(r2，num4)并打印其结果。

```cpp
// C++ program to call a function in main
#include <iostream>
using namespace std;

int add(int num1, int num2)
{
    return (num1 + num2);
}

int main()
{
    int num1 = 12, num2 = 34, num3 = 67, num4 = 12;

    // The innermost add() is computed first, then middle
    // add(), then the outermost add()
    cout << add(add(add(num1, num2), num3), num4);

    return 0;
}
```

**Output:**

```cpp
125

```

函数调用函数的另一个例子如下:–

```cpp
#include <iostream>
using namespace std;

int add(int num1, int num2);
int sub(int num1, int num2);
int mul(int num1, int num2);

int calculator(int num1, int num2, int option)
{
    // calling add function within calculator function
    if (option == 1) {
        return add(num1, num2); 
    }

    // calling sub function within calculator function
    if (option == 2) {
        return sub(num1, num2); 
    }

    // calling mul function within calculator function
    if (option == 3) {
        return mul(num1, num2); 
    }    
}

// function for adding two numbers
int add(int num1, int num2) 
{
    return (num1 + num2);
}

// function for subtracting numbers
int sub(int num1, int num2) 
{
    return (num1 - num2);
}

// function for multiplying two number
int mul(int num1, int num2) 
{
    return (num1 * num2);
}

int main()
{
    int num1 = 10, num2 = 5; // variable

    // giving options for different 
    // calculation(add, sub, mul, div)
    int option;

    option = 1; // Assuming that user inputs 1

    cout << calculator(num1, num2, option);

    return 0;
}
```

**Output:**

```cpp
15

```