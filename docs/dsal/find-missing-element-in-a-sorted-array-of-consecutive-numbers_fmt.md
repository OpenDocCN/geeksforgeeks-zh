# 在连续数字的排序数组中查找缺失的元素

> 原文: [https://www.geeksforgeeks.org/find-missing-element-in-a-sorted-array-of-consecutive-numbers/](https://www.geeksforgeeks.org/find-missing-element-in-a-sorted-array-of-consecutive-numbers/)

给定一个由 `n` 个不同整数组成的数组 `arr[]`。元素按升序排列，缺少一个元素。任务是找到丢失的元素。

**例:**

> **输入:** `arr[] = {1, 2, 4, 5, 6, 7, 8, 9}`
> **输出:** 3
> **输入:** `arr[] = {-4, -3, -1, 0, 1, 2}`
> **输出:** -2
> **输入:** `arr[] = {1, 2, 3, 4}`
> **输出:** -1

**原则:**

> *   **寻找不一致性:** 理想情况下，任何元素与其索引之间的差值必须等于 `arr[0]`。
>     **例如:**
>     `A[] = {1,2,3,4,5}` -> 一致
>     `B[] = {101,102,103,104}` -> 一致
>     `C[] = {1,2,4,5}` -> 不一致，因为 `4-2 != 1`
> *   发现不一致性有助于每次只扫描数组的一半，时间复杂度为 O(logN)。

**算法**

> 1.  找到中间元素并检查它是否一致。
> 2.  如果中间元素一致，检查中间元素与其下一个元素的差值是否大于1，即检查 `arr[mid+1] - arr[mid] > 1`
>     *   如果是，则 `arr[mid]+1` 是缺失的元素。
>     *   如果不是，则我们必须从中间元素开始扫描右半部分数组，并跳回步骤1。
> 3.  如果中间元素不一致，检查中间元素与其前一个元素的差值是否大于1，即检查 `arr[mid] - arr[mid-1] > 1`
>     *   如果是，则 `arr[mid]-1` 是缺失的元素。
>     *   如果不是，则我们将从中间元素开始扫描左半部分数组，并跳回步骤1。

以下是上述方法的实现:

## C++

```cpp
// CPP implementation of the approach
#include<bits/stdc++.h>
using namespace std;

// Function to return the missing element
int findMissing(int arr[], int n)
{

    int l = 0, h = n - 1;
    int mid;

    while (h > l)
    {

        mid = l + (h - l) / 2;

        // Check if middle element is consistent
        if (arr[mid] - mid == arr[0])
        {

            // No inconsistency till middle elements
            // When missing element is just after
            // the middle element
            if (arr[mid + 1] - arr[mid] > 1)
                return arr[mid] + 1;
            else
            {
                // Move right
                l = mid + 1;
            }
        }
        else
        {

            // Inconsistency found
            // When missing element is just before
            // the middle element
            if (arr[mid] - arr[mid - 1] > 1)
                return arr[mid] - 1;
            else
            {
                // Move left
                h = mid - 1;
            }
        }
    }

    // No missing element found
    return -1;
}

// Driver code
int main()
{
    int arr[] = { -9, -8, -7, -5, -4, -3, -2, -1, 0 };
    int n = sizeof(arr)/sizeof(arr[0]);

    cout << (findMissing(arr, n));
}

// This code is contributed by
// Surendra_Gangwar
```

## Java

```java
// Java implementation of the approach
class GFG {

    // Function to return the missing element
    public static int findMissing(int arr[], int n)
    {

        int l = 0, h = n - 1;
        int mid;

        while (h > l) {

            mid = l + (h - l) / 2;

            // Check if middle element is consistent
            if (arr[mid] - mid == arr[0]) {

                // No inconsistency till middle elements
                // When missing element is just after
                // the middle element
                if (arr[mid + 1] - arr[mid] > 1)
                    return arr[mid] + 1;
                else {

                    // Move right
                    l = mid + 1;
                }
            }
            else {

                // Inconsistency found
                // When missing element is just before
                // the middle element
                if (arr[mid] - arr[mid - 1] > 1)
                    return arr[mid] - 1;
                else {

                    // Move left
                    h = mid - 1;
                }
            }
        }

        // No missing element found
        return -1;
    }

    // Driver code
    public static void main(String args[])
    {
        int arr[] = { -9, -8, -7, -5, -4, -3, -2, -1, 0 };
        int n = arr.length;

        System.out.print(findMissing(arr, n));
    }
}
```

## Python 3

```python
# Python implementation of the approach

# Function to return the missing element
def findMissing(arr, n):

    l, h = 0, n - 1
    mid = 0

    while (h > l):

        mid = l + (h - l) // 2

        # Check if middle element is consistent
        if (arr[mid] - mid == arr[0]):

            # No inconsistency till middle elements
            # When missing element is just after
            # the middle element
            if (arr[mid + 1] - arr[mid] > 1):
                return arr[mid] + 1
            else:

                # Move right
                l = mid + 1

        else:

            # Inconsistency found
            # When missing element is just before
            # the middle element
            if (arr[mid] - arr[mid - 1] > 1):
                return arr[mid] - 1
            else:

                # Move left
                h = mid - 1

    # No missing element found
    return -1

# Driver code
arr = [-9, -8, -7, -5, -4, -3, -2, -1, 0 ]
n = len(arr)

print(findMissing(arr, n))

# This code is contributed
# by mohit kumar
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

    // Function to return the missing element
    public static int findMissing(int[] arr, int n)
    {

        int l = 0, h = n - 1;
        int mid;

        while (h > l)
        {

            mid = l + (h - l) / 2;

            // Check if middle element is consistent
            if (arr[mid] - mid == arr[0])
            {

                // No inconsistency till middle elements
                // When missing element is just after
                // the middle element
                if (arr[mid + 1] - arr[mid] > 1)
                    return arr[mid] + 1;
                else
                {

                    // Move right
                    l = mid + 1;
                }
            }
            else
            {

                // Inconsistency found
                // When missing element is just before
                // the middle element
                if (arr[mid] - arr[mid - 1] > 1)
                    return arr[mid] - 1;
                else
                {

                    // Move left
                    h = mid - 1;
                }
            }
        }

        // No missing element found
        return -1;
    }

    // Driver code
    public static void Main()
    {
        int[] arr = { -9, -8, -7, -5, -4, -3, -2, -1, 0 };
        int n = arr.Length;

        Console.WriteLine(findMissing(arr, n));
    }
}

// This code is contributed by Code_Mech
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
<?php
// PHP implementation of the approach

// Function to return the missing element
function findMissing($arr, $n)
{
    $l = 0; $h = $n - 1;

    while ($h > $l)
    {

        $mid = floor($l + ($h - $l) / 2);

        // Check if middle element is consistent
        if ($arr[$mid] - $mid == $arr[0])
        {

            // No inconsistency till middle elements
            // When missing element is just after
            // the middle element
            if ($arr[$mid + 1] - $arr[$mid] > 1)
                return $arr[$mid] + 1;
            else
            {

                // Move right
                $l = $mid + 1;
            }
        }
        else
        {

            // Inconsistency found
            // When missing element is just before
            // the middle element
            if ($arr[$mid] - $arr[$mid - 1] > 1)
                return $arr[$mid] - 1;
            else
            {

                // Move left
                $h = $mid - 1;
            }
        }
    }

    // No missing element found
    return -1;
}

// Driver code
$arr = array( -9, -8, -7, -5, -
               4, -3, -2, -1, 0 );
$n = count($arr);

echo findMissing($arr, $n);

// This code is contributed by Ryuga
?>
```

## java 描述语言

```javascript
<script>
// JavaScript implementation of the approach

// Function to return the missing element
function findMissing(arr, n)
{

    let l = 0, h = n - 1;
    let mid;

    while (h > l)
    {

        mid = l + Math.floor((h - l) / 2);

        // Check if middle element is consistent
        if (arr[mid] - mid == arr[0])
        {

            // No inconsistency till middle elements
            // When missing element is just after
            // the middle element
            if (arr[mid + 1] - arr[mid] > 1)
                return arr[mid] + 1;
            else
            {
                // Move right
                l = mid + 1;
            }
        }
        else
        {

            // Inconsistency found
            // When missing element is just before
            // the middle element
            if (arr[mid] - arr[mid - 1] > 1)
                return arr[mid] - 1;
            else
            {
                // Move left
                h = mid - 1;
            }
        }
    }

    // No missing element found
    return -1;
}

// Driver code
    let arr = [ -9, -8, -7, -5, -4, -3, -2, -1, 0 ];
    let n = arr.length;

    document.write(findMissing(arr, n));

// This code is contributed by Surbhi Tyagi.
</script>
```

**Output:**

```

```

**时间复杂度:** `O(log(N))`
**辅助空间:** `O(1)`