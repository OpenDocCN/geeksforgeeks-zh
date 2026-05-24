# STD::uniform _ real _ distribution 类用 C++ 举例

> 原文:[https://www . geesforgeks . org/STD uniform _ real _-distribution-class-in-c-with-examples/](https://www.geeksforgeeks.org/stduniform_real_-distribution-class-in-c-with-examples/)

在概率论中，[均匀分布函数](https://www.geeksforgeeks.org/mathematics-probability-distributions-set-1/)是指概率定义在一个连续的随机变量上的分布，一个可以取两个数之间的任意值，那么这个分布就称之为连续概率分布。例如，给定一天的温度可以用连续的随机变量来表示，相应的概率分布被称为连续的。

![\[ f(x) = \frac{1}{b-a}, & a\leq x < b\\ \] ](img/6fa2ff6415a8589e2bac3bf570c2c8b3.png "Rendered by QuickLaTeX.com")

[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 在**随机库**中引入了**均匀实分布**类，其成员函数以均匀概率给出来自给定输入范围的随机实数或连续值。
**uniform _ real _ distribution 类中的公共成员函数:**

1.  **运算符():**该函数返回给定范围内的随机值。返回值的数据类型是在模板类初始化期间指定的。任何值的概率都是一样的。该操作的时间复杂度为 0(1)。
    **例:**

    ## 卡片打印处理机(卡片打印处理器的缩写)

```cpp
// C++ code to demonstrate the working of
// operator() function

#include <iostream>

// for uniform_real_distribution function
#include <random>

using namespace std;

int main()
{
    // Here default_random_engine object
    // is used as source of randomness
    // We can give seed also to default_random_engine
    // if psuedorandom numbers are required
    default_random_engine generator;

    double a = 0.0, b = 1.0;

    // Initializing of uniform_real_distribution class
    uniform_real_distribution<double> distribution(a, b);

    // number of experiments
    const int num_of_exp = 10000000;
    // number of ranges
    int n = 100;
    int p[n] = {};
    for (int i = 0; i < num_of_exp; ++ i) {

        // using operator() function
        // to give random values
        double number = distribution(generator);
        ++ p[int(number * n)];
    }

    cout << "Probability of some ranges" << endl;
    // Displaying the probability of some ranges
    // after generating values 10000 times.
    cout << "0.50-0.51"
         << " " << (float)p[50] / (float)num_of_exp << endl;
    cout << "0.60-0.61"
         << " " << (float)p[60] / (float)num_of_exp << endl;
    cout << "0.45-0.46"
         << " " << (float)p[45] / (float)num_of_exp << endl;
    return 0;
}
```