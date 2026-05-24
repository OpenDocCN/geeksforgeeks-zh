# 查找使数组为回文的最小合并操作数

> 原文： [https://www.geeksforgeeks.org/find-minimum-number-of-merge-operations-to-make-an-array-palindrome/](https://www.geeksforgeeks.org/find-minimum-number-of-merge-operations-to-make-an-array-palindrome/)

给定一个正整数数组。 我们需要将给定的数组设为“回文”。 仅允许对数组进行的操作是合并。 合并两个相邻元素意味着用它们的总和替换它们。 任务是找到使给定数组成为“回文”所需的最小合并操作数。

为了使数组成为回文，我们可以简单地将合并操作应用`n-1`次，其中`n`是数组的大小（请注意，单个元素数组总是回文，类似于单个字符串）。 在这种情况下，数组的大小将减小为 1。但是在这个问题上，我们被要求以最少的操作数来完成。

**示例**：

```
Input : arr[] = {15, 4, 15}
Output : 0
Array is already a palindrome. So we
do not need any merge operation.

Input : arr[] = {1, 4, 5, 1}
Output : 1
We can make given array palindrome with
minimum one merging (merging 4 and 5 to
make 9)

Input : arr[] = {11, 14, 15, 99}
Output : 3
We need to merge all elements to make
a palindrome.
```

预期时间复杂度为`O(n)`。

[](https://practice.geeksforgeeks.org/problem-page.php?pid=670)

## 强烈建议您在继续解决方案之前，单击这里进行练习。

令`f(i, j)`为使子数组`arr[i..j]`成为回文式的最小合并操作。 如果`i == j`，答案为 0。我们从 0 开始，而`i`从`n-1`开始。

1.  如果`arr[i] == arr[j]`，则无需对索引`i`或索引`j`进行任何合并操作。 在这种情况下，我们的答案将是`f(i + 1, j-1)`。

2.  否则，我们需要进行合并操作。 出现以下情况。

*   如果`arr[i] > arr[j]`，那么我们应该在索引`j`处进行合并操作。 我们合并索引`j-1`和`j`，并更新`arr[j-1] = arr[j-1] + arr[j]`。 在这种情况下，我们的答案将是`1 + f(i, j-1)`。

*   对于`arr[i] < arr[j]`的情况，更新`arr[i + 1] = arr[i + 1] + arr[i]`。 在这种情况下，我们的答案将是`1 + f(i + 1, j)`。

*   我们的答案将是`f(0, n-1)`，其中`n`是数组`arr[]`的大小。

因此，可以使用两个指针（第一个指针指向数组的开始，第二个指针指向数组的最后一个元素）方法迭代地解决此问题，并保持到目前为止完成的合并操作总数。

以下是上述想法的实现。

## C

```c
// C++ program to find number of operations 
// to make an array palindrome 
#include <bits/stdc++.h> 
using namespace std; 

// Returns minimum number of count operations 
// required to make arr[] palindrome 
int findMinOps(int arr[], int n) 
{ 
    int ans = 0; // Initialize result 

    // Start from two corners 
    for (int i=0,j=n-1; i<=j;) 
    { 
        // If corner elements are same, 
        // problem reduces arr[i+1..j-1] 
        if (arr[i] == arr[j]) 
        { 
            i++; 
            j--; 
        } 

        // If left element is greater, then 
        // we merge right two elements 
        else if (arr[i] > arr[j]) 
        { 
            // need to merge from tail. 
            j--; 
            arr[j] += arr[j+1] ; 
            ans++; 
        } 

        // Else we merge left two elements 
        else
        { 
            i++; 
            arr[i] += arr[i-1]; 
            ans++; 
        } 
    } 

    return ans; 
} 

// Driver program to test above 
int main() 
{ 
    int arr[] = {1, 4, 5, 9, 1}; 
    int n = sizeof(arr)/sizeof(arr[0]); 
    cout << "Count of minimum operations is "
         <<  findMinOps(arr, n) << endl; 
    return 0; 
} 
```

## Java

```java
// Java program to find number of operations 
// to make an array palindrome 

class GFG 
{ 
    // Returns minimum number of count operations 
    // required to make arr[] palindrome 
    static int findMinOps(int[] arr, int n) 
    { 
        int ans = 0; // Initialize result 

        // Start from two corners 
        for (int i=0,j=n-1; i<=j;) 
        { 
            // If corner elements are same, 
            // problem reduces arr[i+1..j-1] 
            if (arr[i] == arr[j]) 
            { 
                i++; 
                j--; 
            } 

            // If left element is greater, then 
            // we merge right two elements 
            else if (arr[i] > arr[j]) 
            { 
                // need to merge from tail. 
                j--; 
                arr[j] += arr[j+1] ; 
                ans++; 
            } 

            // Else we merge left two elements 
            else
            { 
                i++; 
                arr[i] += arr[i-1]; 
                ans++; 
            } 
        } 

        return ans; 
    } 

    // Driver method to test the above function 
    public static void main(String[] args) 
    { 
        int arr[] = new int[]{1, 4, 5, 9, 1} ; 
        System.out.println("Count of minimum operations is "+ 
                                findMinOps(arr, arr.length)); 

    } 
} 
```

## Python

```py
# Python program to find number of operations 
# to make an array palindrome 

# Returns minimum number of count operations 
# required to make arr[] palindrome 
def findMinOps(arr, n): 
    ans = 0 # Initialize result 

    # Start from two corners 
    i,j = 0,n-1
    while i<=j: 
        # If corner elements are same, 
        # problem reduces arr[i+1..j-1] 
        if arr[i] == arr[j]: 
            i += 1
            j -= 1

        # If left element is greater, then 
        # we merge right two elements 
        elif arr[i] > arr[j]: 
            # need to merge from tail. 
            j -= 1
            arr[j] += arr[j+1]  
            ans += 1

        # Else we merge left two elements 
        else: 
            i += 1
            arr[i] += arr[i-1] 
            ans += 1

    return ans 

# Driver program to test above 
arr = [1, 4, 5, 9, 1] 
n = len(arr) 
print("Count of minimum operations is " + str(findMinOps(arr, n))) 

# This code is contributed by Pratik Chhajer 
```

## C#

```cs
// C# program to find number of operations 
// to make an array palindrome 
using System; 

class GFG 
{ 
    // Returns minimum number of count operations 
    // required to make arr[] palindrome 
    static int findMinOps(int []arr, int n) 
    { 
        int ans = 0; // Initialize result 

        // Start from two corners 
        for (int i = 0, j = n - 1; i <= j;) 
        { 
            // If corner elements are same, 
            // problem reduces arr[i+1..j-1] 
            if (arr[i] == arr[j]) 
            { 
                i++; 
                j--; 
            } 

            // If left element is greater, then 
            // we merge right two elements 
            else if (arr[i] > arr[j]) 
            { 
                // need to merge from tail. 
                j--; 
                arr[j] += arr[j + 1] ; 
                ans++; 
            } 

            // Else we merge left two elements 
            else
            { 
                i++; 
                arr[i] += arr[i-1]; 
                ans++; 
            } 
        } 

        return ans; 
    } 

    // Driver Code 
    public static void Main() 
    { 
        int []arr = new int[]{1, 4, 5, 9, 1} ; 
        Console.Write("Count of minimum operations is " + 
                            findMinOps(arr, arr.Length)); 

    } 
} 

// This code is contributed by nitin mittal 
```

## PHP

```php
<?php 
// PHP program to find number 
// of operations to make an 
// array palindrome 

// Returns minimum number of 
// count operations required 
// to make arr[] palindrome 
function findMinOps($arr, $n) 
{ 
    // Initialize result 
    $ans = 1;  

    // Start from two corners 
    for ($i = 0, $j = $n - 1; $i <= $j😉 
    { 
        // If corner elements are same, 
        // problem reduces arr[i+1..j-1] 
        if ($arr[$i] == $arr[$j]) 
        { 
            $i++; 
            $j--; 
        } 

        // If left element is greater, then 
        // we merge right two elements 
        else if ($arr[$i] > $arr[$j]) 
        { 
            // need to merge from tail. 
            $j--; 
            $arr[$j] += $arr[$j + 1] ; 
            $ans++; 
        } 

        // Else we merge 
        // left two elements 
        else
        { 
            $i++; 
            $arr[$i] += $arr[$i - 1]; 
            $ans++; 
        } 
    } 

    return $ans; 
} 

// Driver Code 
$arr[] = array(1, 4, 5, 9, 1); 
$n = sizeof($arr); 
echo "Count of minimum operations is ", 
                 findMinOps($arr, $n) ; 

// This code is contributed by nitin mittal. 
?> 
```

**输出**：

```
Count of minimum operations is 1
```

给定程序的时间复杂度为：`O(n)`。