# c++ STL 中的无序 _ 集合运算符

> 原文:[https://www . geesforgeks . org/unordered _ set-operators-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-operators-in-c-stl/)

无序集在 C++ STL 中提供了两种运算符。这些是:
**语法:**

```cpp
1\. (unordered_set &lhs == unordered_set &rhs)
2\. (unordered_set &lhs != unordered_set &rhs)
```

下面详细讨论这些操作符:

[c++ STL 中的无序 _ 集合==运算符](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl-3/)

“==”是 C++ STL 中的一个运算符，在两个无序集之间执行相等比较运算，**无序 _ 集::运算符==** 是相同的对应运算符函数。
**语法:**

```cpp
(unordered_set &uset1 == unordered_set &uset2)
```

**参数:**该运算符函数引用两个无序集**使用 1** 和**使用 2** 作为要比较的参数。
**返回值:**该方法在比较两个集合后返回一个布尔结果值。比较程序如下:

*   首先比较它们的大小。
*   然后在 ust2 中寻找 ust1 中的每个元素

如果两个条件都满足**则返回真**值，如果条件不满足，则返回**假**值。
下面的程序说明了 C++ 中的无序 _ 集合::运算符==的用法。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{
    // Initialize three unordered sets
    unordered_set<int>
        sample1 = { 10, 20, 30, 40, 50 };
    unordered_set<int>
        sample2 = { 10, 30, 50, 40, 20 };
    unordered_set<int>
        sample3 = { 10, 20, 30, 50, 60 };

    // Compare sample1 and sample2
    if (sample1 == sample2) {

        cout << "sample1 and "
             << "sample2 are equal."
             << endl;
    }
    else {

        cout << "sample1 and "
             << "sample2 are not equal."
             << endl;
    }

    // Compare sample2 and sample3
    if (sample2 == sample3) {

        cout << "sample2 and "
             << "sample3 are equal."
             << endl;
    }
    else {

        cout << "sample2 and "
             << "sample3 are not equal."
             << endl;
    }

    return 0;
}
```

**Output:** 

```cpp
sample1 and sample2 are equal.
sample2 and sample3 are not equal.
```

[无序 _ 集合！= c++ STL 中的运算符](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl-2/)

**！=** 是 C++ STL 中的一个关系运算符，用来比较无序 _ 集合容器之间的等式和不等式。比较按照以下程序进行:

1.  首先，比较大小。
2.  然后，一个容器中的每个元素在另一个容器中查找。

**语法:**

```cpp
unordered_set1 != unordered_set2 
```

**参数:**该方法将两个无序 _ 集合容器**无序 _ 集合 1** 和**无序 _ 集合 2** 作为待检查是否相等的参数。
**返回值:**此方法返回

*   **true:** 如果运算符左侧和右侧的无序集容器相等。
*   **false:** 如果运算符左侧和右侧的无序 _ 集合容器不相等。

下面的例子说明了！=运算符:
**示例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// unordered_set operator!=

#include <cstring>
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{
    unordered_set<string>
        a = { "C++", "Java", "Python" },
        b = { "Java", "Python", "C++" },
        c = { "C#", "Python", "Java" };

    if (a != b) {
        cout << "a and b are not equal\n";
    }
    else {
        cout << "a and b are equal\n";
    }

    if (a != c) {
        cout << "a and c are not equal\n";
    }
    else {
        cout << "a and c are equal\n";
    }

    return 0;
}
```

**Output:** 

```cpp
a and b are equal
a and c are not equal
```

[c++ STL 中的无序集=运算符](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl/)

“=”是 C++ STL 中的一个运算符，它将一个无序 _ 集复制(或移动)到另一个无序 _ 集，而无序 _ 集::运算符=是对应的运算符函数。这个函数有三个版本。

*   第一个版本以无序集的引用作为参数，并将其复制到无序集。
*   第二个版本执行移动分配，即将无序集的内容移动到另一个无序集。
*   第三个版本将初始值设定项列表的内容分配给无序集。

**语法**

```cpp
uset.operator= ( unordered_set& us )
uset.operator= ( unordered_set&& us )
uset.operator= ( initializer list )
```

**参数:**

*   第一个版本以无序集的引用作为参数。
*   第二个版本将无序集的 r 值引用作为参数。
*   第三个版本以初始化列表作为参数。

**返回值:**都返回这个指针的值(*this)。
下面的程序说明了 C++ 中的**无序 _ 集合::运算符=** 。
**程序:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to illustrate the method
// unordered_set::operator=()
#include <iostream>
#include <unordered_set>
using namespace std;

// merge function
template <class T>
T merge(T a, T b)
{
    T t(a);
    t.insert(b.begin(), b.end());
    return t;
}

int main()
{
    unordered_set<int> sample1, sample2, sample3;

    // List initialization
    sample1 = { 7, 8, 9 };
    sample2 = { 9, 10, 11, 12 };

    // Merge both lists
    sample3 = merge(sample1, sample2);

    // copy assignment
    sample1 = sample3;

    // Print the unordered_set list
    for (auto it = sample1.begin(); it != sample1.end(); ++ it)
        cout << *it << " ";
    cout << endl;

    for (auto it = sample2.begin(); it != sample2.end(); ++ it)
        cout << *it << " ";
    cout << endl;

    for (auto it = sample3.begin(); it != sample3.end(); ++ it)
        cout << *it << " ";
    cout << endl;
}
```

**Output:** 

```cpp
10 11 12 7 8 9 
12 11 10 9 
10 11 12 7 8 9
```