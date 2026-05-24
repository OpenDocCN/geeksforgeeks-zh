# c++ 中的 std::replace 和 STD::replace _ if

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdereplace-STD replace _ if-c/

**标准::更换**

为范围[第一个，最后一个]中与旧值相比较的所有元素分配新值。该函数使用运算符==将各个元素与 old_value 进行比较

**功能模板:**

```cpp
void replace (ForwardIterator first, 
 ForwardIterator last,
              const T& old_value,
              const T& new_value)
first, last : 
Forward iterators to the initial and final positions
in a sequence of elelments.
old_value : Value to be replaced.
new_value : Replacement value.

```

**返回值:**
这个函数不返回值。如果找到需要替换的元素，则替换的元素
保持不变。

**示例:**

```cpp
Input : 10 20 30 30 20 10 10 20 
Output : 10 99 30 30 99 10 10 99 
// Replaced value 20 in vector to 99.

Input : 3 5 7 8 9 5 4 
Output : 3 5 7 12 9 5 4  
// Replaced value 8 by 12.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to find and replace the value
// with another value in array
// using std::replace
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    int arr[] = { 10, 20, 30, 30, 20, 10, 10, 20 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // variable containing the old and new values
    int old_val = 20, new_val = 99;

    // print old array
    cout << "Original Array:";
    for (int i = 0; i < n; i++)
        cout << ' ' << arr[i];
    cout << '\n';

    // Function used to replace the values
    replace(arr, arr + n, old_val, new_val);

    // new array after using std::replace
    cout << "New Array:";
    for (int i = 0; i < n; i++)
        cout << ' ' << arr[i];
    cout << '\n';

    return 0;
}
```

**Output**

```cpp
Original Array: 10 20 30 30 20 10 10 20
New Array: 10 99 30 30 99 10 10 99

```

**标准::替换 _if**

为范围[第一个，最后一个]中 **pred** 返回真的所有元素分配 new_value。
**功能模板:**

```cpp
void replace_if (ForwardIterator first, ForwardIterator last,
                   UnaryPredicate pred, const T& new_value)
first, last : Forward iterators to the initial and final positions
in a sequence of elelments.
pred : Unary function that accepts an element in the range as argument, and
returns a value convertible to bool.The returned value indicate whether
the element is to be replaced (if true, it is replaced).
The function shall not modify its argument.
old_value : Value to be replaced.
new_value : Replacement value. 

```

**示例:**

```cpp
Input : 1 2 3 4 5 6 7 8 9 10  
Output : 0 2 0 4 0 6 0 8 0 10  
// Replaced all odd values to 0.

Input : 10 20 30 30 20 10 10 20 
Output : 10 4 30 30 4 10 10 4  
// Replaced all number divisible by 4 to 4.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to find all the elements that are odd
// and replace them with 0.
// using std::replace_if
#include <bits/stdc++.h>
using namespace std;

// Function that is used in std::replace_if
// If number is odd return 1, else 0
// 1 (True) means replace the number
// 0 (False) means does not replace
bool IsOdd(int i)
{
  return ((i % 2) == 1);
}

// Driver code
int main()
{
    int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // print old array
    cout << "Original Array:";
    for (int i = 0; i < n; i++)
        cout << ' ' << arr[i];
    cout << '\n';

    // replacement value
    int new_val = 0;

    // replace_if function
    replace_if(arr, arr + n, IsOdd, new_val);

    // new array after using std::replace
    cout << "New Array:";
    for (int i = 0; i < n; i++)
        cout << ' ' << arr[i];
    cout << '\n';

    return 0;
}
```

**Output**

```cpp
Original Array: 1 2 3 4 5 6 7 8 9 10
New Array: 0 2 0 4 0 6 0 8 0 10

```

您也可以在 **std::replace_if** 中添加任何一种只能有一个参数的函数。
本文由**沙钦·比斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。