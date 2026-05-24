# 在 C++ 中传递和返回对象

> 原文:[https://www . geesforgeks . org/passing-and-return-objects-in-c/](https://www.geeksforgeeks.org/passing-and-returning-objects-in-c/)

在 C++ 中，我们可以将类的对象作为参数传递，也可以像传递和返回其他变量一样从函数中返回它们。这样做不需要特殊的关键字或头文件。

### 将对象作为参数传递

为了将对象作为参数传递，我们将对象名作为参数，同时调用函数，就像我们对其他变量那样。
**语法:**

```cpp
function_name(object_name);
```

**示例:**在这个示例中，有一个类，它有一个整数变量‘a’和一个以对象为参数的函数‘add’。该函数由一个对象调用，并以另一个对象作为参数。在函数内部，参数对象的整数值被添加到调用“add”函数的对象上。在这个方法中，我们可以将对象作为参数传递并修改它们。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to show passing
// of objects to a function

#include <bits/stdc++.h>
using namespace std;

class Example {
public:
    int a;

    // This function will take
    // an object as an argument
    void add(Example E)
    {
        a = a + E.a;
    }
};

// Driver Code
int main()
{

    // Create objects
    Example E1, E2;

    // Values are initialized for both objects
    E1.a = 50;
    E2.a = 100;

    cout << "Initial Values \n";
    cout << "Value of object 1: " << E1.a
         << "\n& object 2: " << E2.a
         << "\n\n";

    // Passing object as an argument
    // to function add()
    E2.add(E1);

    // Changed values after passing
    // object as argument
    cout << "New values \n";
    cout << "Value of object 1: " << E1.a
         << "\n& object 2: " << E2.a
         << "\n\n";

    return 0;
}
```

**Output**

```cpp
Initial Values 
Value of object 1: 50
& object 2: 100

New values 
Value of object 1: 50
& object 2: 150
```