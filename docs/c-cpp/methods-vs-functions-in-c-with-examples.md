# c++ 中方法与函数的比较，示例

> 原文:[https://www . geesforgeks . org/methods-vs-functions-in-c-with-examples/](https://www.geeksforgeeks.org/methods-vs-functions-in-c-with-examples/)

方法是 [OOPs 概念](https://www.geeksforgeeks.org/object-oriented-programming-in-cpp/)中的过程或函数。然而，函数是一组可重用的代码，可以在程序的任何地方使用。这有助于满足反复编写相同代码的需要。它帮助程序员编写模块化代码。

**方法:**

1.  方法的工作原理与函数相同。
2.  方法是在类中定义的。**例如:** [主()在 Java 中](https://www.geeksforgeeks.org/main-method-compulsory-java/)
3.  方法可以是私有的、公共的或受保护的。
4.  该方法仅由其引用/对象调用。例如:如果类有 obj 作为对象名，那么调用方法是:

    ```cpp
    obj.method();

    ```

5.  方法能够对类中包含的数据进行操作
6.  每个对象都有自己的方法，这些方法存在于类中。

**[功能](https://www.geeksforgeeks.org/functions-in-c/) :**

1.  函数是一组语句，接受特定的输入，进行一些计算，最后产生输出。
2.  函数是独立定义的。**例如:** [主()在 C++ ](https://www.geeksforgeeks.org/executing-main-in-c-behind-the-scene/)
3.  默认情况下，函数是公共的。
4.  它可以在整个程序的任何地方访问。
5.  它被称为它的名字本身。
6.  如果需要，它能够返回值。
7.  如果定义了一个函数，那么它对于已经创建的每个对象都是相同的。

下面是用 C++ 说明函数和方法的程序:

**程序 1:**

```cpp
// C++ program to illustrate functions
#include "bits/stdc++.h"
using namespace std;

// Function Call to print array elements
void printElement(int arr[], int N)
{

    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {
        cout << arr[i] << ' ';
    }
}

// Driver Code
int main()
{

    // Given array
    int arr[] = { 13, 15, 66, 66, 37,
                  8, 8, 11, 52 };

    // length of the given array arr[]
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    printElement(arr, N);
    return 0;
}
```

**Output:**

```cpp
13 15 66 66 37 8 8 11 52

```

**程序 2:**

```cpp
// C++ program to illustrate methods
// in class
#include "bits/stdc++.h"
using namespace std;

// Class GfG
class GfG {
private:
    string str = "Welcome to GfG!";

public:
    // Method to access the private
    // member of class
    void printString()
    {

        // Print string str
        cout << str << '\n';
    }
};

// Driver Code
int main()
{

    // Create object of class GfG
    GfG g;

    // Accessing private member of
    // class GfG using public methods
    g.printString();

    return 0;
}
```

**Output:**

```cpp
Welcome to GfG!

```

**程序 3:**

```cpp
// C++ program to illustrate methods
// and functions
#include <iostream>
using namespace std;

// Function call to return string
string offering(bool a)
{
    if (a) {
        return "Apple.";
    }
    else {
        return "Chocolate.";
    }
}

// Class Declaration
class GFG {
public:
    // Method for class GFG
    void guest(bool op)
    {
        if (op == true) {
            cout << "Yes, I want fruit!\n";
        }
        else {
            cout << "No, Thanks!\n";
        }
    }
};

// Driver Code
int main()
{
    bool n = true;

    cout << "Will you eat fruit? ";

    // Create an object of class GFG
    GFG obj;

    // Method invoking using an object
    obj.guest(n);

    if (n == true) {

        // Append fruit using function
        // calling
        cout << "Give an " + offering(n);
    }

    // Giving fruit..Function calling
    else {

        // Append fruit using function
        // calling
        cout << "Give a " + offering(n);
    }

    return 0;
}
```

**Output:**

```cpp
Will you eat fruit? Yes, I want fruit!
Give an Apple.

```