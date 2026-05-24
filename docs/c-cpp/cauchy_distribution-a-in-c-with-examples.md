# c++ 中的柯西分布 a()，示例

> 原文:[https://www . geesforgeks . org/Cauchy _ distribution-a-in-c-with-examples/](https://www.geeksforgeeks.org/cauchy_distribution-a-in-c-with-examples/)

柯西分布::a()函数是 C++ STL 中的一个内置函数，用于返回与柯西分布相关联的分布参数。类 cauchy_distribution 存在于头文件 random 中。在讨论函数的语法之前，先简单介绍一下柯西分布。

**柯西分布**如果随机变量 X 具有以下形式的概率密度函数，
![ f(x)=\frac{1}{\pi b[1+(\frac{x-a}{b})^2]} ](img/5aefb04dd9d7266149134e9d7a480a3e.png "Rendered by QuickLaTeX.com")，则称其遵循带有参数 A 和 b 的柯西分布

其中 a 是指定分布峰值位置的位置参数，b 是指定半峰半宽的比例参数。分布的均值和方差没有定义，但是它的中值和模都存在并且等于 a

**语法:**

```cpp
cauchy_distribution_name.a()
```

**参数:**该功能不接受任何参数。

**返回值:**函数返回与分布相关的分布参数。这个参数被称为柯西分布的峰值位置参数，它决定了向分布形状任一侧的移动。参数是在构造时设置的。

下面的程序说明了 C++ STL 中的柯西分布函数:

**程序 1:**

```cpp
// CPP program to illustrate
// cauchy_distribution::a()
#include <iostream>
#include <random>
using namespace std;

// Driver program
int main()
{
    default_random_engine generator;
    cauchy_distribution<double> d(0.78, 1.45);

    // prints the first value
    cout << "Cauchy distribution: " << d.a();

    return 0;
}
```

**Output:**

```cpp
Cauchy distribution: 0.78

```

**程序 2:**

```cpp
// CPP program to illustrate
// cauchy_distribution::a()
#include <iostream>
#include <random>
using namespace std;

// Driver program
int main()
{
    default_random_engine generator;

    // Define a cauchy distribution with default 
    // parameters a=0.0 and b=1.0
    cauchy_distribution<double> d;

    // prints the first value
    cout << "Cauchy distribution: " << d.a();

    return 0;
}
```

**Output:**

```cpp
Cauchy distribution: 0

```