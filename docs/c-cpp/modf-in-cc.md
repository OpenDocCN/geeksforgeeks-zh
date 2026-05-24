# C/c++

中的 modf()

> 原文:[https://www.geeksforgeeks.org/modf-in-cc/](https://www.geeksforgeeks.org/modf-in-cc/)

在 C++ 中，modf()是用于数学计算的预定义函数。 **math.h** 是各种数学函数所需的头文件。这个库中所有可用的函数都以 double 作为参数，并返回 double 作为结果。

**modf()** 函数将给定的自变量分成两部分，一部分是整数，另一部分是小数。整数部分存储在指针指向的内存地址中，指针作为函数中的第二个参数传递，小数部分由函数返回。

**语法:**

```cpp
double modf(k, &p)

```

> **参数:**
> 
> *   **k:** 将被分成两部分的是值。*   **p:** It is pointer which points to the integer part of **k** after breaking.
>     
>     **返回:**
>     
>     *   The function returns the fractional value of **k**.
>     
>     **错误:**
>     
>     *   这个函数没有引起任何特别的错误。

**与该功能相关的异常**:

*   If anything other then a float, double or integer number is passed, it returns a type error.

    ```cpp
    // CPP program to demonstrate
    // exception of this function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Take any value
        double p, fraction;
        string k = "5.06";

        // Breaks k into two parts
        fraction = modf(k, &p);

        cout << "Integer Value = " << p 
             << endl << "Fraction Value = " 
             << fraction << endl;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    prog.cpp:13:23: error: no matching function for call to 'modf(std::__cxx11::string&, double*)'
      fraction = modf(k, &p);
    .....
    /usr/include/c++/5/cmath:395:3: note: candidate: float std::modf(float, float*)
       modf(float __x, float* __iptr)

    ```

> **注意:** **k** 和 **p** 必须是同一数据类型。

**示例:**

1.  Passing double(float) value as an argument:

    ```cpp
    // CPP program to demonstrate
    // modf() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Take any value
        double k = 5.06, p, fraction;

        // Breaks k into two parts
        fraction = modf(k, &p);

        cout << "Integer Value = " << p 
             << endl << "Fraction Value = " 
             << fraction << endl;

        return 0;
    }
    ```

    **输出**

    ```cpp
    Integer Value = 5
    Fraction Value = 0.06

    ```

2.  **Passing integer value as an argument:**

    ```cpp
    // CPP program to demonstrate
    // modf() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Taking positive value
        double k = 8, p, fraction;

        // Breaks k into two parts
        fraction = modf(k, &p);

        cout << k << " =>";
        cout << "\tInteger Value = " << p 
             << endl << "\tFraction Value = " 
             << fraction << endl;

        // Taking negative value
        k = -8;
        fraction = modf(k, &p);

        cout << k << " =>";
        cout << "\tInteger Value = " << p 
             << endl << "\tFraction Value = "
             << fraction << endl;

        return 0;
    }
    ```

    **输出**

    ```cpp
    8  =>    Integer Value = 8
        Fraction Value = 0
    -8 =>    Integer Value = -8
        Fraction Value = -0

    ```

**注:**如上码，正值给出正输出，负值给出负输出。因此，小数和整数都具有与参数中给定值相同的符号。