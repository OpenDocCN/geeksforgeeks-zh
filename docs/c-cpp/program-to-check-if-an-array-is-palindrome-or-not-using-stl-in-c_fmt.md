# 检查数组是否是回文的程序，在 C++ 中不使用 STL

> 原文：[https://www.geeksforgeeks.org/program-to-check-if-an-array-is-palindrome-or-not-using-stl-in-c/](https://www.geeksforgeeks.org/program-to-check-if-an-array-is-palindrome-or-not-using-stl-in-c/)

给定一个数组，任务是使用 C++ 中的 STL 来确定一个数组是否是回文。

**示例：**

```cpp
Input: arr[] = {3, 6, 0, 6, 3}
Output: Palindrome

Input: arr[] = {1, 2, 3, 4, 5}
Output: Not Palindrome
```

## 进场

*   使用 STL 中提供的`reverse()`方法获得数组的反向。
*   初始化标志以取消设置`int flag = 0`。
*   循环数组直到大小为 n，并检查原始数组和反转数组是否相同。如果未设置`flag = 1`。
*   循环结束后，如果设置了标志，打印`"Not Palindrome"`否则打印`"Palindrome"`。

## 以下是上述方法的实施情况

```cpp
// C++ program to check if an Array
// is Palindrome or not using STL

#include <bits/stdc++.h>
using namespace std;

void palindrome(int arr[], int n)
{
    // Initialise flag to zero.
    int flag = 0;

    // Create another array
    // to store the original array
    int arr2[n];
    memcpy(arr2, arr, n * sizeof(int));

    // Reverse the array
    reverse(arr, arr + n);

    // Check if the array is Palindrome
    for (int i = 0; i < n; i++)
        if (arr[i] != arr2[i]) {
            flag = 1;
            break;
        }

    // Print the result
    if (flag == 0)
        cout << "Palindrome\n";
    else
        cout << "Not Palindrome\n";
}

int main()
{
    // Get the array
    int arr[] = { 1, 2, 3, 2, 1 };

    // Compute the size
    int n = sizeof(arr) / sizeof(arr[0]);

    palindrome(arr, n);

    return 0;
}
```

## Output

```cpp
Palindrome
```

## 相关文章

*   [https://www.geeksforgeeks.org/program-to-check-if-an-array-is-palindrome-or-not/](https://www.geeksforgeeks.org/program-to-check-if-an-array-is-palindrome-or-not/)
*   [https://www.geeksforgeeks.org/program-to-check-if-an-array-is-palindrome-or-not-using-recursion/](https://www.geeksforgeeks.org/program-to-check-if-an-array-is-palindrome-or-not-using-recursion/)