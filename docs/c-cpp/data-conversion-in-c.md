# c++ 中的数据转换

> 原文:[https://www.geeksforgeeks.org/data-conversion-in-c/](https://www.geeksforgeeks.org/data-conversion-in-c/)

A [用户自定义数据](https://www.geeksforgeeks.org/user-defined-data-types-in-c/)类型由用户根据自己的需求设计，编译器不支持此类[数据类型](https://www.geeksforgeeks.org/data-types-in-c/)的自动[类型转换](https://www.geeksforgeeks.org/type-conversion-c/)，因此用户需要根据需要自行设计转换例程。

在不兼容数据类型之间的数据转换中，可能会出现 3 种情况:

*   **将** [**原始数据类型**](https://www.geeksforgeeks.org/primitive-data-type-vs-object-data-type-in-java-with-examples/) **转换为自定义类型:**要执行此转换，思路是在[对象创建](https://www.geeksforgeeks.org/different-ways-to-create-an-object-in-c-sharp/)期间使用[构造函数](https://www.geeksforgeeks.org/constructors-c/)执行类型转换。下面是将 **int** 转换为**自定义**数据类型:
    的例子

**示例:**

## C++

```cpp
// C++ program to illustrate the
// type-conversion
#include <bits/stdc++.h>
using namespace std;

// Time Class
class Time {
    int hour;
    int mins;

public:
    // Default Constructor
    Time()
    {
        hour = 0;
        mins = 0;
    }

    // Parameterized Constructor
    Time(int t)
    {
        hour = t / 60;
        mins = t % 60;
    }

    // Function to print the value
    // of class variables
    void Display()
    {
        cout << "Time = " << hour
             << " hrs and "
             << mins << " mins\n";
    }
};

// Driver Code
int main()
{
    // Object of Time class
    Time T1;
    int dur = 95;

    // Conversion of int type to
    // class type
    T1 = dur;
    T1.Display();

    return 0;
}
```

**Output**

```cpp
Time = 1 hrs and 35 mins
```