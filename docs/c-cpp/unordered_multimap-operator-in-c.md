# 无序 _ 多映射运算符=在 C++ 中

> 原文:[https://www . geesforgeks . org/unordered _ multimap-operator-in-c/](https://www.geeksforgeeks.org/unordered_multimap-operator-in-c/)

**无序 _ 多映射::运算符=** 是 C++ STL 中的一个内置函数，它执行三种类型的任务，如下所述。

1.  **语法**(从不同容器复制元素):

```cpp
*unordered_multimap_name1* operator= (*unordered_multimap_name2*)
```

1.  **参数:**函数不接受任何参数。右边的容器是要将元素复制到左边容器的容器。
    **返回值:**不返回任何东西。
    以下程序说明了上述功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// unordered_multimap::operator=
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample1, sample2;

    // inserts key and element
    // in sample1
    sample1.insert({ 10, 100 });
    sample1.insert({ 50, 500 });

    cout << "Key and Elements of Sample1 before copy  are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\nThe size of sample2 before copy: "
         << sample2.size();

    // operator= to copy
    sample2 = sample1;

    cout << "\nKey and Elements of Sample2 after copy are: ";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:** 

```cpp
Key and Elements of Sample1 before copy  are:{50, 500} {10, 100} 
The size of sample2 before copy: 0
Key and Elements of Sample2 after copy are: {50, 500} {10, 100}
```

1.  **语法**(用于移动不同容器中的元素):

```cpp
*unordered_multimap_name1* operator= (*unordered_multimap_name2*)
```

1.  **参数:**函数不接受任何参数。右边的容器是要将元素从其中移到左边容器的容器。使用运算符=后，右侧容器中的元素将被销毁。
    **返回值:**不返回任何东西。
    以下程序说明了上述功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// unordered_multimap::operator=
#include <bits/stdc++.h>
using namespace std;

// Function to merge two lists
unordered_multimap<char, char> merge(unordered_multimap<char, char> a,
                                     unordered_multimap<char, char> b)
{
    unordered_multimap<char, char> temp(a);
    temp.insert(b.begin(), b.end());
    return temp;
}
int main()
{

    // declaration
    unordered_multimap<char, char> sample1, sample2, sample3;

    // inserts key and element
    // in sample1
    sample1.insert({ 'a', 'A' });
    sample1.insert({ 'g', 'G' });

    // inserts key and element
    // in sample1
    sample2.insert({ 'b', 'B' });
    sample2.insert({ 'c', 'C' });
    sample2.insert({ 'd', 'D' });

    cout << "Key and Elements of Sample1 are: ";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\nKey and Elements of Sample2 are: ";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    // merging and moved
    sample3 = merge(sample1, sample2);
    sample1 = sample3;

    cout << "\n\nKey and Elements of Sample1 are: ";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:** 

```cpp
Key and Elements of Sample1 are: {g, G} {a, A} 
Key and Elements of Sample2 are: {d, D} {b, B} {c, C} 

Key and Elements of Sample1 are: {c, C} {b, B} {d, D} {a, A} {g, G}
```

1.  **语法**(用于分配来自不同*列表*的元素):

```cpp
*unordered_multimap_name1* operator= (*intitializer_list il*)
```

1.  **参数:**它不接受任何参数，它右边的列表将被分配给容器。
    **返回值:**不返回任何东西。
    以下程序说明了上述功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// unordered_multimap::operator=
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration by using operator=
    unordered_multimap<int, int> sample1 = { { 1, 2 }, { 3, 4 }, { 5, 6 } };

    cout << "Key and Elements of Sample1 are: ";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    // declaration by using operator=
    unordered_multimap<char, char> sample2 = { { 'a', 'A' }, { 'b', 'B' }, { 'c', 'C' } };

    cout << "\n\nKey and Elements of Sample1 are: ";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:** 

```cpp
Key and Elements of Sample1 are: {5, 6} {3, 4} {1, 2} 

Key and Elements of Sample1 are: {c, C} {b, B} {a, A}
```