# 为 C++ 17 中的 _ 每 _ n

> 原文:[https://www.geeksforgeeks.org/for_each_n-in-c17/](https://www.geeksforgeeks.org/for_each_n-in-c17/)

C++ 17 技术规范中增加了 **for_each_n** ()函数。它的想法借鉴了*巨蟒*或*哈斯克尔*中*地图*的用法。无论是否有*执行策略*，都可以调用该函数。执行策略允许您决定是利用优化后的新并行功能在多个内核上运行，还是像以前的标准一样按顺序运行。甚至忽略执行策略，因为所有函数都重载了顺序运行的对应函数。

简单地说，for_each_n()有助于对数组(或任何其他线性数据类型)的所有元素应用一个公共函数。它本质上是从给定的迭代器开始，针对该迭代器中固定数量的元素，批量更新一系列元素。

**语法:**

```cpp
InputIt for_each_n( ExecutionPolicy&& policy,
           InputIt first, Size n, UnaryFunction f )

policy: [Optional] The execution policy to use.
The function is overloaded without its use.
first: The iterator to the first element 
you want to apply the operation on.
n: the number of elements to apply the function to.
f: the function object that is applied to the elements.  

```

*(注意:给定的代码需要 C++ 17 或更高版本，可能无法在所有 C++ 17 环境中运行。)*

```cpp
// Requires C++ 17 or 17+
// C++ program to demonstrate the use for_each_n
// using function pointers as lambda expressions.
#include <bits/stdc++.h>
using namespace std;

/* Helper function to modify each element */
int add1(int x)
{
    return (x + 2);
}

int main()
{
    vector<int> arr({ 1, 2, 3, 4, 5, 6 });

    // The initial vector
    for (auto i : arr)
        cout << i << " ";
    cout << endl;

    // Using function pointer as third parameter
    for_each_n(arr.begin(), 2, add1);

    // Print the modified vector
    for (auto i : arr)
        cout << i << " ";
    cout << endl;

    // Using lambda expression as third parameter
    for_each_n(arr.begin() + 2, 2, [](auto& x) { x += 2; });

    // Print the modified vector
    for (auto i : arr)
        cout << i << " ";
    cout << endl;

    return 0;
}
```

输出:

```cpp
1 2 3 4 5 6
2 3 3 4 5 6
2 3 5 6 5 6

```

只有使用[函子](https://www.geeksforgeeks.org/functors-in-cpp/)作为其第三个参数，才能充分利用**的真正威力和灵活性。**

*(注意:给定的代码需要 c++ 17 或更高版本，可能无法在所有 c++ 17 环境中运行。)*

```cpp
// Requires C++ 17 or 17+
// A C++ program to demonstrate the use for_each_n
// using funcctors.
#include <bits/stdc++.h>
using namespace std;

// A Functor
class add_del {
private:
    int n;

public:
    increment(int _n)
        : n(_n)
    {
    }

    // overloading () to create Functor objects
    int operator()(int delta) const
    {
        return n + delta;
    }
};

int main()
{
    vector<int> arr({ 1, 2, 3, 4, 5, 6 });

    // The initial vector
    for (auto i : arr)
        cout << i << " ";
    cout << endl;

    // Using functor as third parameter
    for_each_n(arr.begin(), 2, add_del(1));
    for_each_n(arr.begin() + 2, 2, add_del(2));

    // Print the modified vector
    for (auto i : arr)
        cout << i << " ";
    cout << endl;

    return 0;
}
```

输出:

```cpp
1 2 3 4 5 6
2 3 5 6 5 6

```