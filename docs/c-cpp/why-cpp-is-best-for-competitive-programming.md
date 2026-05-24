# 为什么 C++ 最适合竞技编程？

> 原文:[https://www . geeksforgeeks . org/why-CPP-最适合竞争编程/](https://www.geeksforgeeks.org/why-cpp-is-best-for-competitive-programming/)

[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 是[竞技编程](https://www.geeksforgeeks.org/how-to-begin-with-competitive-programming/)最首选的语言。在本文中，讨论了 C++ 的一些[特性，这些特性使其最适合竞争性编程。](https://www.geeksforgeeks.org/features-of-c/)

[**STL(标准模板库)**](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) **:** C++ 有一个庞大的名为 STL 的库，它是 [C++ 模板](https://www.geeksforgeeks.org/templates-cpp/)的集合，提供通用的编程[数据结构](https://www.geeksforgeeks.org/data-structures/)以及[列表](https://www.geeksforgeeks.org/linked-list-set-1-introduction/)、[栈](https://www.geeksforgeeks.org/stack-data-structure/)、[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)等功能。这使得代码非常短，并提高了编码速度。它是一个由[容器类](https://www.geeksforgeeks.org/containers-cpp-stl/)、算法和[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)组成的库。例如， [**std::min**](https://www.geeksforgeeks.org/stdmin-in-cpp/) 用于找出传递给它的数字中的最小值。如果有多个，它将返回其中的第一个。

**程序 1:**

## C++

```cpp
// C++ program to demonstrate the
// use of min() function

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    double a = 12.123;
    double b = 12.456;

    // Print the minimum of the
    // two numbers
    cout << min(a, b);

    return 0;
}
```

**Output:** 

```cpp
12.123
```

**更快:**就速度而言，C/C++ 比任何其他编程语言都要快。C++ 源代码需要变成机器代码。然而，python 在解释时遵循不同的策略。代码的编译总是比解释快。

**程序 2:**

[下面程序演示如何使用时钟()功能](https://www.geeksforgeeks.org/measure-execution-time-with-high-precision-in-c-c/)测量执行时间:

## C++

```cpp
// C++ program to measure execution
// time using clock() function

#include <bits/stdc++.h>
using namespace std;

// Function whose time taken to
// be measured
void fun()
{
    for (int i = 0; i < 10; i++) {
    }
}

// Driver Code
int main()
{
    // clock_t clock(void) returns the
    // number of clock ticks elapsed
    // after program was launched.
    clock_t start, end;

    // Recording the starting
    // clock tick
    start = clock();

    fun();

    // Recording the end clock tick
    end = clock();

    // Calculating total time taken
    // by the program
    double time_taken
        = double(end - start)
          / double(CLOCKS_PER_SEC);

    cout << "Time taken by program is: "
         << fixed
         << time_taken
         << setprecision(5);

    cout << " sec " << endl;

    return 0;
}
```

**Output:** 

```cpp
Time taken by program is: 0.000001 sec
```

**Simple constructions:**C++ 是一种简单的语言，即更接近于[的低级语言](https://www.geeksforgeeks.org/difference-between-high-level-and-low-level-languages/)，因此用 c++ 编写代码要比用 [Java](https://www.geeksforgeeks.org/java/) 容易得多。此外，这使得 C++ 中的代码生成过程更加简单、优化和快速(也就是说，就像在 Java 中一样，不需要先将代码转换为字节码，然后再转换为机器码)。

**广泛使用:** C++ 被全球 75%的程序员认为是竞争性编程的最佳选择，因为它通常比 Java 和 [Python](https://www.geeksforgeeks.org/python-programming-language/) 更快，而且大部分资源都是 C++ 提供的。

[模板](https://www.geeksforgeeks.org/templates-cpp/):模板是 C++ 中一个简单却非常强大的工具。简单的想法是将数据类型作为参数传递，这样我们就不需要为不同的数据类型编写相同的代码。

**程序 3:**

以下是演示模板的程序:

## C++

```cpp
// C++ program to demonstrate template
#include <iostream>
using namespace std;

// Generic function to find minimum
// of 2 data types
template <typename T>
T Min(T x, T y)
{
    return (x < y) ? x : y;
}

// Driver Code
int main()
{
    cout << Min(7, 3) << endl;
    cout << Min('z', 'a') << endl;

    return 0;
}
```

**Output:** 

```cpp
3
a
```

[**Snippets**](https://www.geeksforgeeks.org/custom-c-user-snippet-in-visual-studio-code/)**:**Snippets 提供了一种将常用代码或函数实现为更大代码段的简单方法。程序员不用一遍又一遍地重写相同的代码，而是可以将代码保存为一个代码片段，并简单地将代码片段拖放到任何需要的地方。通过使用代码片段，程序员和 web 开发人员还可以将公共代码段组织成类别，从而创建一个更干净的开发环境。它还提高了编码速度，有助于编码竞赛等。

**程序 4:**

下面是一个可以在竞争性编程中使用的示例代码片段:

## C++

```cpp
// C++ program to demonstrate snippets
#include <bits/stdc++.h>
using namespace std;

#define MOD 1000000007
#define endl "\n"
#define lli long long int
#define ll long long
#define mp make_pair
#define pb push_back

void solve()
{
    // Write down your desired
    // code here
    cout << "Write your code here";
}

// Driver Code
int main()
{
    // Handle t number of testcases
    int t = 1;
    while (t--) {
        solve();
    }
    return 0;
}
```

**Output:** 

```cpp
Write your code here
```