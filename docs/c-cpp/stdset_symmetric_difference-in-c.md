# 用例子在 C++ 中设置 _ 对称 _ 差

> 原文:[https://www . geesforgeks . org/stdset _ symmetric _ difference-in-c/](https://www.geeksforgeeks.org/stdset_symmetric_difference-in-c/)

**两个排序范围的对称差**
两个集合之间的对称差是由其中一个集合中存在的元素形成的，而不是由另一个集合中存在的元素形成的。在每个范围内的等价元素中，被丢弃的是那些在调用之前以现有顺序出现的元素。复制的元素也会保留现有顺序。
第一个版本使用运算符<比较元素，第二个版本使用 comp。两个元素 a 和 b 被认为是等价的，如果(！(a < b) & &！(b < a))或 if(！comp(a，b) & &！比较(b，a))。
范围内的元素应已订购。
1。**使用默认运算符< :**
语法:

```cpp
Template :
OutputIterator set_symmetric_difference (InputIterator1 first1, InputIterator1 last1,
                                         InputIterator2 first2, InputIterator2 last2,
                                         OutputIterator result);

Parameters :

first1, last1
Input iterators to the initial and final positions of the first
sorted sequence. The range used is [first1, last1), which contains
all the elements between first1 and last1, including the element
pointed by first1 but not the element pointed by last1.

first2, last2
Input iterators to the initial and final positions of the second
sorted sequence. The range used is [first2, last2).

result
Output iterator to the initial position of the range where the
resulting sequence is stored.
The pointed type shall support being assigned the value of an
element from the other ranges.

comp
Binary function that accepts two arguments of the types pointed
by the input iterators, and returns a value convertible to bool.
The function shall not modify any of its arguments.
This can either be a function pointer or a function object.

The ranges shall not overlap.

Return Type :
An iterator to the end of the constructed range.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: set_symmetric_difference
#include <algorithm> // std::set_symmetric_difference, std::sort
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

    // Sorting both the arrays
    std::sort(first, first + 5);
    std::sort(second, second + 5);

    // Using default operator<
    it = std::set_symmetric_difference(first, first + 5,
    second, second + 5, v.begin());

    std::cout << "The symmetric difference has "
              << (it - v.begin()) << " elements:\n";
    for (st = v.begin(); st != it; ++ st)
        std::cout << ' ' << *st;
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
First array contains : 5 10 15 20 25
Second array contains : 50 40 30 20 10

The symmetric difference has 6 elements:
 5 15 25 30 40 50
```

2.**使用自定义功能:**
语法:

```cpp
Template :
OutputIterator set_symmetric_difference (InputIterator1 first1, InputIterator1 last1,
                                         InputIterator2 first2, InputIterator2 last2,
                                         OutputIterator result, Compare comp);

Parameters :

first1, last1, first2, last2, result are same as described above.

comp
Binary function that accepts two arguments of the types pointed
by the input iterators, and returns a value convertible to bool.
The function shall not modify any of its arguments.
This can either be a function pointer or a function object.

The ranges shall not overlap.

Return Type :
An iterator to the end of the constructed range.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: set_symmetric_difference
#include <algorithm> // std::set_symmetric_difference, std::sort
#include <iostream> // std::cout
#include <vector> // std::vector

// Custom function
bool comp(int a, int b)
{
    return a < b;
}

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

    // Sorting both the arrays
    std::sort(first, first + 5);
    std::sort(second, second + 5);

    // Using default operator<
    it = std::set_symmetric_difference(first, first + 5,
                                       second, second + 5, v.begin(), comp);

    std::cout << "The symmetric difference has "
              << (it - v.begin()) << " elements:\n";
    for (st = v.begin(); st != it; ++ st)
        std::cout << ' ' << *st;
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
First array contains : 5 10 15 20 25
Second array contains : 50 40 30 20 10

The symmetric difference has 6 elements:
 5 15 25 30 40 50
```

**可能的应用:**用于查找存在于一个容器中而不存在于另一个容器中的元素。
1。用于查找不同时上两个班的**学生名单。**两个班的学生都在名单上。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: set_symmetric_difference
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // students attending first class
    std::vector<string> class1{ "Samir", "Manoj", "Pranav", "Rajesh" };

    // students attending second class
    std::vector<string> class2{ "Samir", "Junaid", "Manoj", "Pankaj", "Arpit" };

    cout << "Students attending first class are : ";
    for (auto i : class1) {
        cout << i << " ";
    }
    cout << "\nStudents attending second class are : ";
    for (auto i : class2) {
        cout << i << " ";
    }

    // to store the result of symmetric difference
    std::vector<string> result(10);

    std::vector<string>::iterator it;

    // finding symmetric difference
    it = set_symmetric_difference(class1.begin(),
                                  class1.end(), class2.begin(), class2.end(), result.begin());

    cout << "\n\nList of students that are not taking both classes :";

    for (std::vector<string>::iterator i = result.begin(); i != it; i++) {
        cout << *i << " ";
    }
    return 0;
}
```

输出:

```cpp
Students attending first class are : Samir Manoj Pranav Rajesh 
Students attending second class are : Samir Junaid Manoj Pankaj Arpit 

List of students that are not taking both classes :Junaid Pankaj Arpit Pranav Rajesh 
```

2.它也可以用来**从两个列表中找到不在两个列表中的数字。**
程序如上。
本文由**沙钦毕斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。