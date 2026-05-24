# 是 C/C++

中的 isgreater()

> 原文:[https://www.geeksforgeeks.org/isgreater-in-cc/](https://www.geeksforgeeks.org/isgreater-in-cc/)

在 C++ 中，isgreater()是用于数学计算的预定义函数。 **math.h** 是各种数学函数所需的头文件。
是一个 greater()函数，用于检查给函数的第一个参数是否大于给函数的第二个参数。意思是如果 **a** 是第一个参数， **b** 是第二个参数，则检查 **a > b** 是否存在。
**语法:**

```cpp
bool isgreater(a, b)
Parameters:
a, b => These two are the parameters whose value we want to compare.
Result:
The function will return the true if a>b else it returns false.

Error: 
No error occurs with this function.
Exception: 
If a or b or both is NaN,
then the function raised an exception and return false(0).
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
    double f1 = nan("1");
    bool result;

    // Since f1 value is NaN so
    // with any value of a, the function
    // always return false(0)
    result = isgreater(f1, a);
    cout << f1 << " isgreater than " << a
         << ": " << result;

    return 0;
}
```

**输出:**

```cpp
nan isgreater than 5: 0
```

*   **节目:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// the use of isgreater function
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
    // is false(0)
    result = isgreater(a, b);
    cout << a << " isgreater than " << b
         << ": " << result << endl;

    char x = 'd';

    // Since 'd' ascii value is greater
    // than b variable so answer
    // is true(1)
    result = isgreater(x, b);
    cout << x << " isgreater than " << b
         << ": " << result;

    return 0;
}
```

*   输出:

```cpp
5 isgreater than 8: 0
d isgreater than 8: 1
```

*   该函数可用于任何基于比较的排序算法。让我们在[冒泡排序](https://www.geeksforgeeks.org/bubble-sort/) :
    中使用它

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate the
// use of isgreaterequal function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // taking inputs
    int arr[] = { 5, 2, 8, 3, 4 };
    int n = sizeof(arr) / sizeof(arr[0]);

    for (int i = 0; i < n - 1; i++)
    {
        for (int j = 0; j < n - i - 1; j++)
        {
            if (isgreater(arr[j], arr[j + 1]))
            {
                int k = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = k;
            }
        }
    }

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << ", ";
    }
    return 0;
}
```

*   输出:

```cpp
Sorted array: 2, 3, 4, 5, 8, 
```