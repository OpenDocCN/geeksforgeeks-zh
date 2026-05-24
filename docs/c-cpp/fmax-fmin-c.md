# c++ 中的 fmax()和 fmin()

> 原文:[https://www.geeksforgeeks.org/fmax-fmin-c/](https://www.geeksforgeeks.org/fmax-fmin-c/)

fmax()和 fmin()函数在 **cmath** 头文件中定义。

1.  **fmax() function:** The syntax of this function is:

    ```cpp
    double fmax (double x, double y);
    float fmax (float x, float y);
    long double fmax (long double x, long double y);

    ```

    该函数的输入是两个 float 类型的值，double 或 long double。该函数返回两个输入值中的最大值。

    下面是展示 fmax()函数工作原理的 C++ 示例程序:

    ```cpp
    // CPP program to show working
    // of fmax() function.

    #include <cmath>
    #include <iomanip>
    #include <iostream>

    using namespace std;

    int main()
    {
        double val;

        // Find maximum value when both the inputs
        // are positive.
        val = fmax(10.0, 1.0);
        cout << fixed << setprecision(4)
             << "fmax(10.0, 1.0) = " << val << "\n";

        // Find maximum value when inputs have
        // opposite sign.
        val = fmax(-10.0, 1.0);
        cout << fixed << setprecision(4)
             << "fmax(-10.0, 1.0) = " << val << "\n";

        // Find maximum value when both the inputs
        // are negative.
        val = fmax(-10.0, -1.0);
        cout << fixed << setprecision(4)
             << "fmax(-10.0, -1.0) = " << val << "\n";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    fmax(10.0, 1.0) = 10.0000
    fmax(-10.0, 1.0) = 1.0000
    fmax(-10.0, -1.0) = -1.0000

    ```