# c++ STL 中的无序 _ 集合==运算符

> 原文:[https://www . geesforgeks . org/unordered _ set-operator-in-c-STL-3/](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl-3/)

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
**程序:**

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