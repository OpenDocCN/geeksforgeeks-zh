# 是 C/C++

中的 isgreaterequal()

> 原文:[https://www.geeksforgeeks.org/isgreaterequal-in-cc/](https://www.geeksforgeeks.org/isgreaterequal-in-cc/)

在 C++ 中，isgreaterequal()是用于数学计算的预定义函数。 **math.h** 是各种数学函数所需的头文件。

isgreaterequal()函数用于检查给函数的第一个参数是否大于或等于给函数的第二个参数。意思是如果 **a** 是第一个参数， **b** 是第二个参数，那么检查 **a > =b** 是否存在。

**语法:**

```cpp
bool isgreaterequal(a, b)

```

> **参数:**
> 
> *   **a, b =>** These two are the parameters whose value we want to compare.
>     
>     **结果:**
>     
>     *   The function will return the true if a>=b else it returns false.
>     
>     **错误:**
>     
>     *   这个函数没有特别的错误。

**与该功能相关的异常**:

*   If **a** or **b** or both is NaN then the function raised an exception and return false(0).

    ```cpp
    // CPP code to illustrate
    // the exception of function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Take any values
        float a = 5.5;
        double f1 = nan("1");
        bool result;

        // Since f1 value is NaN so
        // with any value of a, the function
        // always return false(0)
        result = isgreaterequal(a, f1);
        cout << a << " isgreaterequal " << f1
             << ": " << result;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    5.5 isgreaterequal nan: 0

    ```

**示例:**

*   **程序 1:**

    ```cpp
    // CPP code to illustrate
    // the use of isgreaterequal function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Take two any values
        int a, b;
        bool result;
        a = 5;
        b = 8;

        // Since 'a' is not greater
        // than equal to 'b' so answer
        // is false(0)
        result = isgreaterequal(a, b);
        cout << a << " isgreaterequal to " << b
             << ": " << result << endl;

        a = 8;
        b = 5;

        // Since 'a' is greater
        // than 'b' so answer
        // is true(1)
        result = isgreaterequal(a, b);
        cout << a << " isgreaterequal to " << b
             << ": " << result;

        return 0;
    }
    ```

    输出:

    ```cpp
    5 isgreaterequal to 8: 0
    8 isgreaterequal to 5: 1

    ```

    **注意:**使用该函数，您可以将任何数据类型与任何其他数据类型进行比较。

*   **Program 2:**

    ```cpp
    // CPP code to illustrate
    // the use of isgreaterequal function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Take two any values
        bool result;
        float a = 80.23;
        int b = 82;

        // Since 'a' is not greater
        // than equal to 'b' so answer
        // is false(0)
        result = isgreaterequal(a, b);
        cout << a << " isgreaterequal to " << b
             << ": " << result << endl;

        char x = 'b';

        // Since 'b' ascii value is greater
        // than variable a so answer
        // is true(1)
        result = isgreaterequal(x, a);
        cout << x << " isgreaterequal to " << a
             << ": " << result;

        return 0;
    }
    ```

    输出:

    ```cpp
    80.23 isgreaterequal to 82: 0
    b isgreaterequal to 80.23: 1

    ```

**应用**

我们可以使用 isgreaterequal()函数来比较两个值，就像在**中使用**循环来打印任意数字(比如 12)的表格一样。

```cpp
// CPP code to illustrate
// the use of isgreaterequal function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    for (int i = 1;
         isgreaterequal(10, i);
         i++) {
        cout << "12 x " << i << " = "
             << 12 * i << endl;
    }

    return 0;
}
```

**输出:**

```cpp
12 x 1 = 12
12 x 2 = 24
12 x 3 = 36
12 x 4 = 48
12 x 5 = 60
12 x 6 = 72
12 x 7 = 84
12 x 8 = 96
12 x 9 = 108
12 x 10 = 120

```