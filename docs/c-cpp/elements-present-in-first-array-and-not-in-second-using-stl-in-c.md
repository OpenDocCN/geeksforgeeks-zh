# 在 C++ 中使用 STL 时，元素出现在第一个数组中，而不是第二个数组中

> 原文:[https://www . geesforgeks . org/elements-in-first-array-and-not-in-second-use-STL-in-c/](https://www.geeksforgeeks.org/elements-present-in-first-array-and-not-in-second-using-stl-in-c/)

给定两个数组，我们的任务是使用 C++ 中的 STL 找到第一个数组中存在但第二个数组中不存在的数字

**示例:**

```cpp
Input: a[] = {1, 2, 3, 4, 5, 10}, b[] = {2, 3, 1, 0, 5}
Output: 4 10

Input:a[] = {4, 3, 5, 9, 11}, b[] = {4, 9, 3, 11, 10};
Output: 5

```

**方法:**在 STL 中，可以使用 [set_difference()](https://www.geeksforgeeks.org/std-set_difference-in-cpp/) 方法来寻找‘A-B’，其中 A 是第一个数组，B 是第二个数组。

**语法:**

> OutputIterator set _ different(InputIterator1 第一个 1，input iterator 1 最后一个 1，InputIterator2 第一个 2，InputIterator2 最后一个 2，output iterator 结果)；

下面是上述方法的实现:

```cpp
// C++ simple program to
// find elements which are
// not present in second array

#include <bits/stdc++.h>
using namespace std;

// Function for finding
// elements which are there
// in a[] but not in b[].
void findMissing(int a[], int b[],
                 int n, int m)
{

    // Declare a vector to store the result
    vector<int> v(n + m);

    // And an iterator to traverse the vector
    vector<int>::iterator it;

    // Sort the given arrays
    sort(a, a + n);
    sort(b, b + m);

    // Find the elements in a[]
    // which are not in b[]
    it = set_difference(a, a + n, b, b + m, v.begin());

    // Now resize the vector to the existing count
    v.resize(it - v.begin());

    // Print the results
    cout << "The elements in a[]"
         << " which are not in b[]:\n";
    for (it = v.begin(); it != v.end(); ++ it)
        cout << *it << "  ";
    cout << endl;
}

// Driver code
int main()
{
    int a[] = { 1, 2, 6, 3, 4, 5 };
    int b[] = { 2, 4, 3, 1, 0 };
    int n = sizeof(a) / sizeof(a[0]);
    int m = sizeof(b) / sizeof(b[1]);
    findMissing(a, b, n, m);
    return 0;
}
```

**Output:**

```cpp
The elements in a[] which are not in b[]:
5  6

```