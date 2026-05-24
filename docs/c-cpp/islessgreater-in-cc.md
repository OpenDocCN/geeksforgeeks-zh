# C/c++

中的 is less more()

> 原文:[https://www.geeksforgeeks.org/islessgreater-in-cc/](https://www.geeksforgeeks.org/islessgreater-in-cc/)

在 C++ 中，islessgreater()是用于数学计算的预定义函数。math.h 是各种数学函数所需的头文件。
islesslater()函数用于检查给函数的第一个参数是否小于或大于给函数的第二个参数。意思是如果 **a** 是第一个参数， **b** 是第二个参数，则检查 **a > b || a < b** 是否存在。
**语法:**

```cpp
bool islessgreater(a, b)
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
    double f1 = nan("2.0");
    bool result;

    // Since f1 value is NaN so
    // with any value of a, the function
    // always return false(0)
    result = islessgreater(f1, a);
    cout << f1 << " islessgreater than " << a
         << ": " << result;

    return 0;
}
```

输出:

```cpp
nan islessgreater than 5: 0
```

**例:**

*   **程序:**

    ## 卡片打印处理机(卡片打印处理器的缩写)

    ```cpp
    // CPP code to illustrate
    // the use of islessgreater function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // Take two any values
        float a, b;
        bool result;
        a = 10.2;
        b = 8.5;

        // Since 'a' is not less than 'b'
        // but greater than 'b' so answer
        // is true(1)
        result = islessgreater(a, b);
        cout << a << " islessgreater than " << b
             << ": " << result << endl;

        int x = 2;

        // Since 'x' is not greater than 'b'
        // but less than 'a' variable so answer
        // is true(1)
        result = islessgreater(x, a);
        cout << x << " islessgreater than " << a
             << ": " << result << endl;

        a = 8.5;

        // Since value of 'a' and 'b' are
        // equal so answer is false(0)
        result = islessgreater(a, b);
        cout << a << " islessgreater than " << b
             << ": " << result;

        return 0;
    }
    ```

**输出:**

```cpp
10.2 islessgreater than 8.5: 1
2 islessgreater than 10.2: 1
8.5 islessgreater than 8.5: 0
```

**应用:**
这个功能可以在各个地方使用，其中一个可以在线性搜索。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate the
// use of islessgreater function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // taking inputs
    int arr[] = { 5, 2, 8, 3, 4 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // Lets we want to search for 1 in
    // the arr array
    int a = 1;
    int flag = 0;

    for (int i = 0; i < n; i++) 
    {
        if (islessgreater(arr[i], a)) 
        {
            flag = 1;
        }
    }

    if (flag == 0) 
    {
        cout << a << " is present in array";
    }

    else 
    {
        cout << a << " is not present in array";
    }
    return 0;
}
```

**输出:**

```cpp
1 is not present in array
```