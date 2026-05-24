# c++ 中 log()函数

> 原文:[https://www.geeksforgeeks.org/log-function-cpp/](https://www.geeksforgeeks.org/log-function-cpp/)

**c++ 中的 log()函数:**c++ 中的 Log()函数返回参数中传递的参数的自然对数(以-e 为底的对数)。
T3】

> 返回自然对数的语法:
> 结果= log(x)
> 
> 返回参数对数(以 10 为底的对数)的语法。
> 结果= log10(x)

参数可以是任何数据类型，如 **int、double 或 float 或 long double。**

**Log()** 函数根据以下条件返回值:

..a)如果 x>1，则为正
..b)如果 0 < x < 1 返回负值
..c)如果 x=1，则返回 0
..d)如果 x=0，则返回 **-inf**
..e)如果 x < 0，则返回 **NaN** (不是数字)

```cpp
// CPP program to implement log() function
#include <bits/stdc++.h>
using namespace std;

// function to evaluate natural logarithm base-e
double valueE(double d)
{
    return log(d);
}

// function to evaluate logarithm base-10
double value10(double d)
{
    return log10(d);
}

// driver program to test the above function
int main()
{
    double d = 10;
    cout << "The logarithm value(base-e) of " << d 
         << " is " << valueE(d) << endl;
    cout << "The logarithm value(base-10) of " << d 
         << " is " << value10(d) << endl;
    return 0;
}
```

输出:

```cpp
The logarithm value(base-e) of 10 is 2.30259
The logarithm value(base-10) of 10 is 1

```

**应用:**
log()函数的应用之一是计算与 log 相关的值，例如，在寻找[礼貌数字](https://www.geeksforgeeks.org/n-th-polite-number/)时，我们需要将公式写成代码，为此我们可以使用 log()函数。下面给出的是 log()函数的一个实现。

```cpp
// CPP program to find Nth polite number
#include <bits/stdc++.h>
using namespace std;

// function to evaluate n-th polite number
double polite(double n)
{
    n += 1;
    double base = 2;
    return n + (log((n + (log(n) /
                 log(base))))) / log(base);
}

// driver code
int main()
{
    double n = 7;
    cout << (int)polite(n);
    return 0;
}
```

输出:

```cpp
11 

```