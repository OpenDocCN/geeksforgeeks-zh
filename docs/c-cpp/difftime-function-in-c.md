# c++ 中的 difftime()函数

> 原文:[https://www.geeksforgeeks.org/difftime-function-in-c/](https://www.geeksforgeeks.org/difftime-function-in-c/)

**difftime()** 函数在 **ctime** 头文件中定义。difftime()函数用于计算每秒两次的差值。

**语法:**

```cpp
double difftime(time_t end, time_t start);
```

**参数:**此方法接受两个参数:

*   **Start:** The time _ t object is the start time.
*   **End:** The time _ t object is the end time.

**返回:**该函数以秒为单位返回两次之间的**差值。**

**例:-**

```cpp
// C++ program to demonstrate
// example of difftime() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    time_t start, ending;
    long addition;

    time(&start);
    for (int i = 0; i < 20000; i++) {
        for (int j = 0; j < 20000; j++);
    }
    for (int i = 0; i < 20000; i++) {
        for (int j = 0; j < 20000; j++);
    }
    for (int i = 0; i < 20000; i++) {
        for (int j = 0; j < 20000; j++);
    }
    time(&ending);
    cout << "Total time required = "
         << difftime(ending, start)
         << " seconds " << endl;
    return 0;
}
```

**输出:**

```cpp
Total time required = 2 seconds

```