# std::none_of in C++

> 原文: [https://www.geeksforgeeks.org/stdnone_of-in-c/](https://www.geeksforgeeks.org/stdnone_of-in-c/)

如果 `pred` 为范围 [`first`, `last`] 中的所有元素返回 `false`，或者如果范围为空，则返回 `true`，否则返回 `false`。

语法:

```cpp
Template :
bool none_of(InputIterator first, InputIterator last,
                                 UnaryPredicate pred);
```

`first`, `last`
`InputIterator` 类型的迭代器，指向序列的初始位置和最终位置。使用的范围是 [`first`, `last`]，它包含 `first` 和 `last` 之间的所有元素，包括 `first` 指向的元素，但不包括 `last` 指向的元素。

`pred`
一元函数，接受范围内的一个元素作为参数，并返回可转换为 `bool` 的值。返回的值指示该元素是否满足此函数检查的条件。该函数不应修改其参数。它可以是函数指针或函数对象。

返回类型：
如果 `pred` 对范围 [`first`, `last`] 中的所有元素都返回 `false`，或者该范围为空，则返回 `true`；否则返回 `false`。

## 示例 1：基本用法

```cpp
// CPP program to illustrate std :: none_of
#include <iostream> // cout
#include <algorithm> // none_of
using namespace std;

// function to check whether the
// element is negative or not
bool comp(int a) {  return a < 0;  }

// Driver code
int main()
{
    int arr[] = { 2, 4, 6, 8, 12, 0 };
    int n = sizeof(arr)/sizeof(arr[0]);

    cout << "Array contains :";
    for (int i = 0; i < n; i++)
        cout << ' ' << arr[i];
    cout << "\n";

    if (none_of(arr, arr+n, comp))
        cout << "No negative elements in the range.\n";
    else
        cout << "There is at least one negative"
                " element in the array range.\n";
    return 0;
}
```

**Output**

```cpp
Array contains : 2 4 6 8 12 0
No negative elements in the range.
```

## 实际应用

`std::none_of` 函数如果某个条件对范围 [`first`, `last`] 中的所有元素都返回 `false`，或者如果范围为空，则返回 `true`，否则返回 `false`。

### 1. 检查数组是否包含所有偶数或奇数或两者。

```cpp
// CPP program to illustrate std :: none_of
#include <iostream> // cout
#include <algorithm> // none_of
using namespace std;

// functions to check whether the
// element is even or odd
bool isEven(int a) { return (a % 2); }
bool isOdd(int a)  { return (a % 2 == 0); }

// Driver code
int main()
{
    int arr[] = { 2, 4, 6, 8, 12, 0 };
    int n = sizeof(arr)/sizeof(arr[0]);

    cout << "Array contains :";
    for (int i = 0; i < n; i++)
        cout << ' ' << arr[i];
    cout << "\n";

    bool even = none_of(arr, arr + n, isEven);
    bool odd =  none_of(arr, arr + n, isOdd);

    if ((!even) && (!odd))
        cout << "Contains both even and"
                " odd number\n";
    else if ((!even) && odd)
        cout << "Contains odd number only\n";
    else if (even && (!odd))
        cout << "Contains even number only\n";
    else
        cout << "Array is empty\n";

    return 0;
}
```

**Output**

```cpp
Array contains : 2 4 6 8 12 0
Contains even number only
```