# c++ 中 std::set::下界与 std::下界的区别

> 原文:[https://www . geeksforgeeks . org/stdsetlower-bound 和-stdlower-bound-in-c/](https://www.geeksforgeeks.org/difference-between-stdsetlower_bound-and-stdlower_bound-in-c/)之间的差异

**先决条件:**[c++ 中的随机访问迭代器](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)[c++ 中的双向迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)。

**STD::lower _ bound in c++ :**
[lower _ bound()](https://www.geeksforgeeks.org/lower_bound-in-cpp/)方法在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中用于返回一个迭代器，该迭代器指向范围**【第一个，最后一个】**中的第一个元素，该元素的值不小于给定值。这意味着该函数返回仅大于该数字的下一个最小数字的索引。

**std::set::lower_bound 在 C++ 中:**
[set::lower _ bound()](https://www.geeksforgeeks.org/set-lower_bound-function-in-c-stl/)是 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中的内置函数，它返回一个指向容器中元素的迭代器，该元素相当于参数中传递的 **K** 。如果在[集合容器](https://www.geeksforgeeks.org/set-in-cpp-stl/)中不存在 K，该函数返回一个迭代器，指向刚好大于 **K** 的下一个元素。如果参数中传递的键超过了容器中的最大值，则返回的迭代器指向 set 容器中的最后一个元素。

下面是**标准::下界**和**标准::集合::下界:**的区别

| 没有。 | 标准::下限() | std::set::下界() |
| one | **语法:** std::下界(ForwardIterator 优先，ForwardIterator 最后，const T & val)。 | **语法:**标准::下限(常量值类型&值)。 |
| Two | 标准::下界有随机访问迭代器和非随机访问迭代器。 | 标准::集合::下界有双向迭代器。 |
| three | 这个函数优化了比较的次数，这对于随机访问迭代器是有效的。 | 这个函数使用双向迭代器优化了比较的次数 |
| four | 对于随机访问迭代器，运行时间复杂度为 0(log<sub>2</sub>N)，但是对于非随机访问迭代器，运行时间复杂度为 0(N)。 | 由于其二叉查找树实现，运行时间复杂度始终为 0(log<sub>2</sub>N)。 |

下面是带有 [CPU 执行时间](https://www.geeksforgeeks.org/computer-organization-performance-of-computer/)的程序，将说明两个功能的运行时间。

**std::下界()**的程序说明:

```cpp
// C++ program to illustrate
// std::set::lower_bound
#include <bits/stdc++.h>
#include <sys/time.h>
using namespace std;

// Function whose time is to
// be measured
void fun()
{
    // Initialise the set
    set<int> s;

    // Insert element in the set
    for (int i = 0; i < 10; i++) {
        s.insert(i);
    }

    // Use lower_bound() function
    // to find 5
    set<int>::iterator it;
    it = lower_bound(s.begin(), s.end(), 5);
}

// Driver Code
int main()
{
    // Use function gettimeofday()
    // can get the time
    struct timeval start, end;

    // Start timer
    gettimeofday(&start, NULL);

    // unsync the I/O of C and C++.
    ios_base::sync_with_stdio(false);

    // Function Call
    fun();

    // Stop timer
    gettimeofday(&end, NULL);

    // Calculating total time taken
    // by the program.
    double time_taken;

    time_taken = (end.tv_sec
                  - start.tv_sec)
                 * 1e6;

    time_taken = (time_taken
                  + (end.tv_usec
                     - start.tv_usec))
                 * 1e-6;

    cout << "Time taken by program is : "
         << fixed
         << time_taken << setprecision(6);
    cout << " sec" << endl;
    return 0;
}
```

**Output:**

```cpp
Time taken by program is : 0.000046 sec

```

用于说明**标准的程序:**

```cpp
// C++ program to illustrate
// std::lower_bound
#include <bits/stdc++.h>
#include <sys/time.h>
using namespace std;

// Function whose time is to
// be measured
void fun()
{
    // Initialise the set
    set<int> s;

    // Insert element in the set
    for (int i = 0; i < 10; i++) {
        s.insert(i);
    }

    // Use set::lower_bound() function
    // to find 5
    set<int>::iterator it;
    it = s.lower_bound(5);
}

// Driver Code
int main()
{
    // Use function gettimeofday()
    // can get the time
    struct timeval start, end;

    // Start timer
    gettimeofday(&start, NULL);

    // unsync the I/O of C and C++.
    ios_base::sync_with_stdio(false);

    fun();

    // Stop timer
    gettimeofday(&end, NULL);

    // Calculating total time taken
    // by the program.
    double time_taken;

    time_taken = (end.tv_sec
                  - start.tv_sec)
                 * 1e6;

    time_taken = (time_taken
                  + (end.tv_usec
                     - start.tv_usec))
                 * 1e-6;

    cout << "Time taken by program is : "
         << fixed
         << time_taken << setprecision(6);
    cout << " sec" << endl;
    return 0;
}
```

**Output:**

```cpp
Time taken by program is : 0.000039 sec

```