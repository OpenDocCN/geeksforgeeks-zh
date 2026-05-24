# 排序和旋转数组中的最大元素

> 原文:[https://www . geeksforgeeks . org/排序旋转数组中的最大元素/](https://www.geeksforgeeks.org/maximum-element-in-a-sorted-and-rotated-array/)

给定在某个未知点旋转的不同元素的排序数组 **arr[]** ，任务是找到其中的最大元素。
**例:**

> **输入:** arr[] = {3，4，5，1，2}
> **输出:** 5
> **输入:** arr[] = {1，2，3}
> **输出:** 3

**方法:**一个简单的解决方法是遍历整个数组并找到最大值。这个解决方案需要 O(n)个时间。
我们可以用二分搜索法在 O(Logn)做。如果我们仔细看看上面的例子，我们可以很容易地找出以下模式:

*   最大元素是下一个小于它的唯一元素。如果没有下一个较小的元素，则没有旋转(最后一个元素是最大值)。我们通过与**中间–1**和**中间+ 1** 的元素进行比较来检查中间元素的这种情况。
*   如果最大元素不在中间(既不在中间也不在中间+ 1)，则最大元素位于左半部分或右半部分。
    1.  如果中间元素大于最后一个元素，则最大元素位于左半部分。
    2.  否则最大元素位于右半部分。

以下是上述方法的实现:

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

// Function to return the maximum element
int findMax(int arr[], int low, int high)
{

    if (high == low)
        return arr[low];

    // Find mid
    int mid = low + (high - low) / 2;
  // Check if mid reaches 0 ,it is greater than next element or not
     if(mid==0 && arr[mid]>arr[mid+1])
       {
               return arr[mid];
       }

    // Check if mid itself is maximum element
    if (mid < high && arr[mid + 1] < arr[mid] && mid>0 && arr[mid]>arr[mid-1]) {
        return arr[mid];
    }

    // Decide whether we need to go to
    // the left half or the right half
    if (arr[low] > arr[mid]) {
        return findMax(arr, low, mid - 1);
    }
    else {
        return findMax(arr, mid + 1, high);
    }
}

// Driver code
int main()
{
    int arr[] = { 6,5,4,3,2,1};
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << findMax(arr, 0, n - 1);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java implementation of the approach
class GFG
{

// Function to return the maximum element
static int findMax(int arr[], int low, int high)
{

    // If there is only one element left
    if (high == low)
        return arr[low];

    // Find mid
    int mid = low + (high - low) / 2;
  // Check if mid reaches 0 ,it is greater than next element or not
  if(mid==0 && arr[mid]>arr[mid+1])
  {
    return arr[mid];
  }

    // Decide whether we need to go to
    // the left half or the right half
    if (arr[low] > arr[mid])
    {
        return findMax(arr, low, mid - 1);
    }
    else
    {
        return findMax(arr, mid + 1, high);
    }
}

// Driver code
public static void main(String[] args)
{
    int arr[] = { 6,5,4,3,2,1 };
    int n = arr.length;
    System.out.println(findMax(arr, 0, n - 1));
}
}
```

## 蟒蛇 3

```cpp
# Python3 implementation of the approach

# Function to return the maximum element
def findMax(arr, low, high):

    # If there is only one element left
    if (high == low):
        return arr[low]

    # Find mid
    mid = low + (high - low) // 2
    # Check if mid reaches 0 ,it is greater than next element or not
    if(mid==0 and arr[mid]>arr[mid+1]):
          return arr[mid]

    # Check if mid itself is maximum element
    if (mid < high and arr[mid + 1] < arr[mid] and mid>0 and arr[mid]>arr[mid-1]):
        return arr[mid]

    # Decide whether we need to go to
    # the left half or the right half
    if (arr[low] > arr[mid]):
        return findMax(arr, low, mid - 1)
    else:
        return findMax(arr, mid + 1, high)

# Driver code
arr = [6,5,4,3,2,1]
n = len(arr)
print(findMax(arr, 0, n - 1))
```

## C#

```cpp
// C# implementation of the approach
using System;

class GFG
{

// Function to return the maximum element
static int findMax(int []arr,
                   int low, int high)
{

    // If there is only one element left
    if (high == low)
        return arr[low];

    // Find mid
    int mid = low + (high - low) / 2;
    // Check if mid reaches 0 ,it is greater than next element or not
    if(mid==0 && arr[mid]>arr[mid+1])
        return arr[mid];

    // Check if mid itself is maximum element
    if (mid < high && arr[mid + 1] < arr[mid] && mid>0 && arr[mid]>arr[mid-1])
    {
        return arr[mid];
    }

    // Decide whether we need to go to
    // the left half or the right half
    if (arr[low] > arr[mid])
    {
        return findMax(arr, low, mid - 1);
    }
    else
    {
        return findMax(arr, mid + 1, high);
    }
}

// Driver code
public static void Main()
{
    int []arr = { 6,5, 1, 2, 3, 4 };
    int n = arr.Length;

    Console.WriteLine(findMax(arr, 0, n - 1));
}
}
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP implementation of the approach

// Function to return the maximum element
function findMax($arr, $low, $high)
{

    // This condition is for the case when
    // array is not rotated at all
    if ($high <= $low)
        return $arr[$low];

    // Find mid
    $mid = $low + ($high - $low) / 2;
   // Check if mid reaches 0 ,it is greater than next element or not
    if ($mid==0 && $arr[$mid]>$arr[$mid-1])
          return $arr[0];

    // Check if mid itself is maximum element
    if ($mid < $high && $arr[$mid + 1] < $arr[$mid] && $mid > 0 && $arr[$mid]>$arr[$mid-1])
    {
        return $arr[$mid];
    }
    // Decide whether we need to go to
    // the left half or the right half
    if ($arr[$low] > $arr[$mid])
    {
        return findMax($arr, $low, $mid - 1);
    }
    else
    {
        return findMax($arr, $mid + 1, $high);
    }
}

// Driver code
$arr = array(5,6,1,2,3,4);
$n = sizeof($arr);
echo findMax($arr, 0, $n - 1);
```

## java 描述语言

```cpp
<script>
// Java script implementation of the approach

// Function to return the maximum element
function findMax(arr,low,high)
{
    // If there is only one element left
    if (high == low)
        return arr[low];

    // Find mid
    let mid = low + (high - low) / 2;
    // Check if mid reaches 0 ,it is greater than next element or not
    if(mid==0 && arr[mid]>arr[mid+1])
    {
        return arr[mid];
    }

    // Check if mid itself is maximum element
    if (mid < high && arr[mid + 1] < arr[mid] && mid>0 && arr[mid]>arr[mid-1])
    {
        return arr[mid];
    }

    // Decide whether we need to go to
    // the left half or the right half
    if (arr[low] > arr[mid])
    {
        return findMax(arr, low, mid - 1);
    }
    else
    {
        return findMax(arr, mid + 1, high);
    }
}

// Driver code

    let arr = [ 5, 6, 1, 2, 3, 4 ];
    let n = arr.length;
    document.write(findMax(arr, 0, n-1 ));
</script>
```

**Output:** 

```cpp
6
```