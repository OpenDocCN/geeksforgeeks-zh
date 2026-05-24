# std::none_of in C++

> 原文:[https://www.geeksforgeeks.org/stdnone_of-in-c/](https://www.geeksforgeeks.org/stdnone_of-in-c/)

如果 pred 为范围[第一个，最后一个]中的所有元素返回 false，或者如果范围为空，则返回 true，否则返回 false。
语法:

```cpp
Template :
bool none_of(InputIterator first, InputIterator last,
                                 UnaryPredicate pred);
first, last
Input iterators to the initial and final positions in
a sequence. The range used is [first, last], which 
contains all the elements between first and last, 
including the element pointed by first but not the
element pointed by last.

pred
Unary function that accepts an element in the range
as argument and returns a value convertible to bool. 
The value returned indicates whether the element 
fulfills the condition checked by this function.
The function shall not modify its argument.
This can either be a function pointer or a function
object. 

Return type :
true if pred returns false for all the elements in 
the range [first, last] or if the range is empty, 
and false otherwise.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate std :: none_of
#include <iostream> // cout
#include <algorithm> // none_of
using namespace std;

// function to check whether the
// element is negative or not
bool comp(int a) {  return a < 0;  }

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

**实际应用:**
std :: none_of 函数如果某个条件对范围[第一个，最后一个]中的所有元素都返回 false，或者如果范围为空，则返回 true，否则返回 false。
1。**检查数组是否包含所有偶数或奇数或两者。**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate std :: none_of
#include <iostream> // cout
#include <algorithm> // none_of
using namespace std;

// functions to check whether the
// element is even or odd
bool isEven(int a) { return (a % 2); }
bool isOdd(int a)  { return (a % 2 == 0); }

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
    bool odd =  none_of(arr, arr + n, isOdd);

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