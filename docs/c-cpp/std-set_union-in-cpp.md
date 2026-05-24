# 标准::C++ 中的 set _ union

> 原文:[https://www.geeksforgeeks.org/std-set_union-in-cpp/](https://www.geeksforgeeks.org/std-set_union-in-cpp/)

**两个排序范围的并集**
两个集合的并集是由其中一个集合或两个集合中的元素组成的。第二个范围中的元素在第一个范围中具有等效元素，这些元素不会复制到结果范围中。
第一个版本使用运算符<比较元素，第二个版本使用 comp。两个元素 a 和 b 被认为是等价的，如果(！(a < b) & &！(b < a))或 if(！comp(a，b) & &！比较(b，a))。
范围内的元素应已订购。
1。**使用默认运算符< :**

```cpp
Template :
OutputIterator set_union (InputIterator1 first1, InputIterator1 last1,
                          InputIterator2 first2, InputIterator2 last2,
                          OutputIterator result);

Parameters :

first1, last1
Input iterators to the initial and final positions of the first
sorted sequence. The range used is [first1, last1], which contains
all the elements between first1 and last1, including the element
pointed by first1 but not the element pointed by last1.

first2, last2
Input iterators to the initial and final positions of the second
sorted sequence. The range used is [first2, last2].

result
Output iterator to the initial position of the range where the
resulting sequence is stored.

comp
Binary function that accepts two arguments of the types pointed by
the input iterators, and returns a value convertible to bool.
The function shall not modify any of its arguments.
This can either be a function pointer or a function object.

The ranges shall not overlap.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: set_union
#include <algorithm> // std::set_union, std::sort
#include <iostream> // std::cout
#include <vector> // std::vector

// Driver code
int main()
{
    int first[] = { 5, 10, 15, 20, 25 };
    int second[] = { 50, 40, 30, 20, 10 };
    int n = sizeof(first) / sizeof(first[0]);

    // Print first array
    std::cout << "First array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << first[i];
    std::cout << "\n";

    // Print second array
    std::cout << "Second array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << second[i];
    std::cout << "\n\n";

    std::vector<int> v(10);
    std::vector<int>::iterator it, st;

    std::sort(first, first + n);
    std::sort(second, second + n);

    // Using default function
    it = std::set_union(first, first + n, second,
                        second + n, v.begin());

    std::cout << "The union has " << (it - v.begin())
              << " elements:\n";
    for (st = v.begin(); st != it; ++ st)
        std::cout << ' ' << *st;
    std::cout << '\n';

    return 0;
}
```

**输出:**

```cpp
First array contains : 5 10 15 20 25
Second array contains : 50 40 30 20 10

The union has 8 elements:
 5 10 15 20 25 30 40 50

```

2.**使用自定义函数:**
语法:

```cpp
Template :
OutputIterator set_union (InputIterator1 first1, InputIterator1 last1,
                          InputIterator2 first2, InputIterator2 last2,
                          OutputIterator result, Compare comp);

Parameters :

first1, last1, first2, last2, result are same as above.

comp
Binary function that accepts two arguments of the types pointed by
the input iterators, and returns a value convertible to bool.
The function shall not modify any of its arguments.
This can either be a function pointer or a function object.

The ranges shall not overlap.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate use of
// std :: set_symmetric_difference
#include <iostream>
#include <algorithm>
#include <vector>
#include <string>

using namespace std;

// Driver code
int main()
{
    string first[] = { "Sachin", "Rakesh",
                       "Sandeep", "Serena" };
    string second[] = { "Vaibhav", "Sandeep",
                          "Rakesh", "Neha" };
    int n = sizeof(first) / sizeof(first[0]);

    // Print students of first list
    cout << "Students in first subject :";
    for (int i = 0; i < n; i++)
        cout << " " << first[i];
    cout << "\n";

    // Print students of second list
    cout << "Students in second subject :";
    for (int i = 0; i < n; i++)
        cout << " " << second[i];
    cout << "\n\n";

    vector<string> v(10);
    vector<string>::iterator it, st;

    // Sorting both the list
    sort(first, first + n);
    sort(second, second + n);

    // Using default operator<
    it = set_union(first, first + n, second,
                          second + n, v.begin());

    cout << "Students attending both subjects are :\n";
    for (st = v.begin(); st != it; ++ st)
        cout << ' ' << *st;
    cout << '\n';

    return 0;
}
```

**输出:**

```cpp
Students in first subject : Sachin Rakesh Sandeep Serena
Students in second subject : Vaibhav Sandeep Rakesh Neha

Students attending both subjects are :
Neha Rakesh Sachin Sandeep Serena Vaibhav

```

**可能的应用:**用于查找存在于一个容器或两个容器中的元素。
1。它可以用来**找到所有同时参加这两个科目的学生名单。**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate use of
// std :: set_symmetric_difference
#include <algorithm>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

// Driver code
int main()
{
    string first[] = { "John", "Bob", "Mary", "Serena" };
    string second[] = { "Jim", "Mary", "John", "Bob" };
    int n = sizeof(first) / sizeof(first[0]);

    // Print students of first list
    cout << "Students in first subject :";
    for (int i = 0; i < n; i++)
        cout << " " << first[i];
    cout << "\n";

    // Print students of second list
    cout << "Students in second subject :";
    for (int i = 0; i < n; i++)
        cout << " " << second[i];
    cout << "\n\n";

    vector<string> v(10);
    vector<string>::iterator it, st;

    // Sorting both the list
    sort(first, first + n);
    sort(second, second + n);

    // Using default operator<
    it = set_union(first, first + n, second, second + n,
                   v.begin());

    cout << "Students attending both subjects are :\n";
    for (st = v.begin(); st != it; ++ st)
        cout << ' ' << *st;
    cout << '\n';

    return 0;
}
```

**输出:**

```cpp
Students in first subject : Sachin Rakesh Sandeep Serena
Students in second subject : Vaibhav Sandeep Rakesh Neha

Students attending both subjects are :
Neha Rakesh Sachin Sandeep Serena Vaibhav

```

2.它也可以用来求两个集合并集。
程序如上。
本文由**沙钦·毕斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。