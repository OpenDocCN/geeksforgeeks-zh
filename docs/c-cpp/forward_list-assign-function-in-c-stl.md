# c++ STL 中的 forward_list assign()函数

> 原文:[https://www . geesforgeks . org/forward _ list-assign-function-in-c-STL/](https://www.geeksforgeeks.org/forward_list-assign-function-in-c-stl/)

forward_list::assign()是 C++ STL 中的一个函数，它将新内容赋给一个 forward list，替换其当前内容，并根据需要调整其大小。
**语法:**

```cpp
Version 1:forward_list_name.assign(iterator it1, iterator it2)
Version 2:forward_list_name.assign(int n, val)
Version 3:forward_list_name.assign(initializer_list li)
```

**参数:**该功能接受不同版本的不同参数，讨论如下:

*   **迭代器:**第一个版本以两个迭代器为参数。新元素由范围[it1，it2]中的每个元素构成，即它包括 it1 和 it2 之间的所有元素，包括由 it1 取消引用的元素，但不包括由 it2 指向的元素。
*   **n 和 val:** 在第二个版本中，创建了 n 个元素，每个元素都用值 val 初始化。
*   **初始值设定项列表:**在第三个版本中，创建了新的内容，这些内容以相同的顺序用作为初始值设定项列表传递的值的副本进行初始化。

**返回值**该函数不返回值。
函数 forward_list::assign 的三个版本在以下程序中说明:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate the
// forward_list::assign() function

#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> sample1;
    forward_list<int> sample2;

    // Create n elements in
    // sample1 and initialize all
    // Of them with 3
    sample1.assign(5, 3);

    // Initialize sample2 with elements in
    // the range [sample1.begin(), sample1.end)
    sample2.assign(sample1.begin(), sample1.end());

    // Display sample1
    cout << "sample1: ";
    for (int& x : sample1)
        cout << x << " ";

    cout << endl;

    // Display sample2
    cout << "sample2: ";
    for (int& x : sample2)
        cout << x << " ";
}
```

**Output:** 

```cpp
sample1: 3 3 3 3 3 
sample2: 3 3 3 3 3
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate the
// forward_list::assign() function

#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> sample;

    // Initialize sample with an
    // Initialization list
    sample.assign({ 4, 5, 7, 8, 9, 45 });

    // Display sample
    cout << "sample: ";
    for (int& x : sample)
        cout << x << " ";
}
```

**Output:** 

```cpp
sample: 4 5 7 8 9 45
```