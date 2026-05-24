# STD::is _ 在 C++ 中排序

> 原文:[https://www.geeksforgeeks.org/stdis_sorted-in-cpp/](https://www.geeksforgeeks.org/stdis_sorted-in-cpp/)

C++ 函数 std :: is_sorted 检查范围[第一个，最后一个]中的元素是否按升序排序。使用 **<** 运算符比较元素。
STD 有两种变体::is_sorted:

1.  **不使用二元谓语**

```cpp
bool is_sorted( ForwardIt first, ForwardIt last );
first, last : the range of elements to examine
Return value : 
true: if the elements are in non-decreasing order.
false: any element in increasing order.
```

1.  **示例:**
    给定一个大小为 n 的容器，并且范围在[0 … n]之间，编写一个程序来检查它是否按升序排序。数组中允许相等的值，并且两个连续的相等值被视为已排序。

```cpp
Input : 2 5 9 4      /*Range = 3*/
Output : Sorted in given range.

Input : 3 5 1 9     /*Range = 3*/
Output : Not sorted in given range.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std::is_sorted
// without binary predicate
#include <iostream>
#include <algorithm>

// Driver Code
int main()
{
    int A[] = { 10, 11, 15, 12 };

    // Index 0 to 2
    int range1 = 3;

    // Index 0 to 3
    int range2 = 4;

    // Condition if container is sorted or not in range1
    if (std::is_sorted(A, A + range1)) {
        std::cout << "Sorted in the range : " << range1 << std::endl;
    } else {
        std::cout << "Not Sorted in the range : " << range1 << std::endl;
    }

    // Condition if container is sorted or not in range2
    if (std::is_sorted(A, A + range2)) {
        std::cout << "Sorted in the range : " << range2 << std::endl;
    } else {
        std::cout << "Not Sorted in the range : " << range2 << std::endl;
    }
    return 0;
}
```

1.  输出:

```cpp
Sorted in the range : 3
Not Sorted in the range : 4
```

1.  我们在这里讨论了其他方法。

2.  **使用二元谓语**

```cpp
bool is_sorted (ForwardIt first, ForwardIt last, Compare comp);
first, last : the range of elements to examine
comp : binary predicate
Return value : 
true: if the elements are in non-decreasing order.
false: any element in increasing order.
```

1.  示例:
    给定一个仅由字符组成的字符串。检查字符是否按排序顺序排列。此外，在比较时忽略案例，即“f”>“A”

```cpp
Input : AHZP
Output : Not Sorted

Input : Boy
Output : Sorted
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std::is_sorted
// using binary predicate
#include <iostream>
#include <algorithm>

using namespace std;

// Binary predicate
bool ignore_case(char a, char b)
{
    // Converts both characters to lowercase and checks if a <= b
    return (tolower(a) <= tolower(b));
}

// Function that checks if string is sorted while ignoring the case
bool check_if_sorted(string str)
{
    // Function call to is_sorted with binary predicate ignore_case
    return is_sorted(str.begin(), str.end(), ignore_case);
}

// Driver code
int main()
{
    // String which is to be checked
    string str = "tOY";

    // Function returned true, string is sorted
    if (check_if_sorted(str)) {
        cout << "Sorted";
    }
    // Function returned false, string not sorted
    else {
        cout << "Not sorted";
    }

    return 0;
}
```

1.  输出:

```cpp
Not sorted
```

1.  **时间复杂度:**复杂度在第一个和最后一个之间的距离是线性的:比较元素对，直到发现不匹配。

本文由 [**罗希特·塔普利亚尔**](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。