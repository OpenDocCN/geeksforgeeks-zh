# 使用 boost 多精度库进行大数阶乘

> 原文：[https://www.geeksforgeeks.org/factorial-large-number-using-boost-multiprecision-library/](https://www.geeksforgeeks.org/factorial-large-number-using-boost-multiprecision-library/)

我们已经给出了一个大数，现在我们可以使用 `boost` 多重精度库很容易地找出这个大数的阶乘。`Boost` 库在当前的 1.53.0 版本中包含了一个新的[多精度库](http://www.boost.org/doc/libs/1_66_0/libs/multiprecision/doc/html/index.html)，面向需要 64 位以上精度的 C++ 程序员。

示例：

```
Input: 100
Output: 933262154439441526816992388562667004...

Input: 50
Output: 3041409320171337804361260816606476884...
```

```cpp
// CPP program to find factorial of large
// number using boost library.
#include <bits/stdc++.h>
#include <boost/multiprecision/cpp_int.hpp>
using boost::multiprecision::cpp_int;
using namespace std;

cpp_int Factorial(int number)
{
    cpp_int num = 1;
    for (int i = 1; i <= number; i++)
        num = num * i;
    return num;
}

int main()
{
    int number = 100;
    cpp_int fact = Factorial(number);
    cout << fact << endl;
    return 0;
}
```

输出：

```