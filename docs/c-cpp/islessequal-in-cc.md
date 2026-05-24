# C/c++

中的 islessequal()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/islaqual-in-cc/

在 C++ 中，islessequal()是 **math.h** 中的预定义函数。用于检查第一个浮点数是否小于或等于第二个浮点数。与简单比较相比，它提供的优势是，它在不引发浮点异常的情况下进行比较。例如，如果两个参数中的一个是 NaN，那么它返回 false 而不引发异常。

**语法:**

```cpp
bool isgreaterequal(a, b)

```

> **参数:**
> 
> *   **a，b = >** 这两个是我们要比较其值的参数。
> 
> **结果:**
> 
> *   如果 a <= b，函数将返回真，否则返回假。
> 
> **错误:**
> 
> *   No error occurs with this function.
>     
>     例外:
>     
>     
>     *   如果 **a** 或 **b** 或两者都是 NaN，则该函数引发异常并返回 false(0)。

下面给出了这方面的说明

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
    result = islessequal(a, f1);
    cout << a << " islessequal " << f1
         << ": " << result;

    return 0;
}
```

**输出:**

```cpp
5.5 islessequal nan: 0

```

**示例:**

*   **Program 1:**

    ```cpp
    // CPP code to illustrate
    // the use of islessequal function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Take two any values
        float a, b;
        bool result;
        a = 5.2;
        b = 8.5;

        // Since 'a' is less than
        // equal to 'b' so answer
        // is true(1)
        result = islessequal(a, b);
        cout << a << " islessequal to " << b
             << ": " << result << endl;

        int x = 8;
        int y = 5;

        // Since 'x' is not less
        // than equal to 'y' so answer
        // is false(0)
        result = islessequal(x, y);
        cout << x << " islessequal to " << y
             << ": " << result;

        return 0;
    }
    ```

    **注意:**使用该函数，您可以将任何数据类型与任何其他数据类型进行比较。

*   **Program 2:**

    ```cpp
    // CPP code to illustrate
    // the use of islessequal function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Take any two values
        bool result;
        float a = 80.23;
        int b = 82;

        // Since 'a' is less
        // than equal to 'b' so answer
        // is true(1)
        result = islessequal(a, b);
        cout << a << " islessequal to " << b
             << ": " << result << endl;

        char x = 'c';

        // Since 'c' ascii value(99) is not
        // less than variable a so answer
        // is false(0)
        result = islessequal(x, a);
        cout << x << " islessequal to " << a
             << ": " << result;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    80.23 islessequal to 82: 1
    c islessequal to 80.23: 0

    ```

**应用:**
有各种各样的应用，我们可以使用 islessequal()函数来比较两个值，就像在**中使用的一样，而**循环打印前 10 个自然数。

```cpp
// CPP code to illustrate
// the use of islessequal function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int i = 1;
    while (islessequal(i, 10)) {
        cout << i << " ";
        i++ ;
    }
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5 6 7 8 9 10 

```