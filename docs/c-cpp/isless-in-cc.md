# C/c++

中的 isless()

> 原文:[https://www.geeksforgeeks.org/isless-in-cc/](https://www.geeksforgeeks.org/isless-in-cc/)

在 C++ 中，isless()是用于数学计算的预定义函数。 **math.h** 是各种数学函数所需的头文件。
isless()函数用于检查给函数的第一个参数是否小于给函数的第二个参数。意思是如果 **a** 是第一个参数， **b** 是第二个参数，则检查 **a < b** 是否存在。
**语法:**

```cpp
bool isless(a, b)
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// the exception of function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any values
    int a = 5;
    double b = nan("1");
    bool result;

    // Since b value is NaN so
    // with any value of a, the function
    // always return false(0)
    result = isless(a, b);
    cout << a << " isless than " << b
         << ": " << result;

    return 0;
}
```

**输出:**

```cpp
5 isless than nan: 0
```

**例:**

*   **程序:**

    ## 卡片打印处理机(卡片打印处理器的缩写)

    ```cpp
    // CPP code to illustrate
    // the use of isless function
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
        // than 'b' so answer
        // is true(1)
        result = isless(a, b);
        cout << a << " isless than " << b
             << ": " << result << endl;

        char x = 'a';

        // Since 'a' ascii value is less
        // than b variable so answer
        // is true(1)
        result = isless(x, b);
        cout << x << " isless than " << b
             << ": " << result;

        return 0;
    }
    ```

**输出:**

```cpp
5 isless than 8: 1
a isless than 8: 0
```

**注意:**使用该函数，您可以将任何数据类型与任何其他数据类型进行比较。
**应用程序**
有多种应用程序，我们可以使用 isless()函数来比较两个值，就像在 while 循环中打印前 9 个自然数一样。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// the use of isless function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int i = 1;
    while (isless(i, 10)) {
        cout << i << " ";
        i++ ;
    }
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5 6 7 8 9 
```