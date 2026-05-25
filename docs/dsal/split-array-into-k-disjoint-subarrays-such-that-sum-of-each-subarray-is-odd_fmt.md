# 将数组拆分成 K 个不相交的子数组，使得每个子数组的和为奇数。

> 原文: [https://www.geeksforgeeks.org/split-array-into-k-disjoint-subarrays-such-that-sum-of-each-subarray-is-odd/](https://www.geeksforgeeks.org/split-array-into-k-disjoint-subarrays-such-that-sum-of-each-subarray-is-odd/)

给定一个包含 `N` 个元素的数组 `arr[]`，任务是将数组划分为 `K` (`1 ≤ K ≤ N`) 个子数组，每个子数组的元素之和为奇数。分割数组后打印每个子数组的起始索引（基于 1 的索引），如果不存在这样的子数组，则打印 `-1`。

**注:** 对于所有子数组 `S1`，`S2`，`S3`，…，`SK`：
*   `S1`，`S2`，`S3`，…，`SK` 的交集应为空。
*   `S1`，`S2`，`S3`，…，`SK` 的并集应该等于原数组。

**示例:**

> **输入:** `N = 5`，`arr[] = {7, 2, 11, 4, 19}`，`K = 3`
> **输出:** `1 3 5`
> **解释:**
> 当给定的数组 `arr[]` 被分成 `K = 3` 个部分时，可能的子数组是：`{7, 2}`，`{11, 4}` 和 `{19}`。
>
> **输入:** `N = 5`，`arr[] = {2, 4, 6, 8, 10}`，`K = 3`
> **输出:** `-1`
> **说明:**
> 不可能将数组 `arr[]` 划分为 `K = 3` 个子数组，因为所有元素都是偶数，每个子数组的和也是偶数。

**方法:** 可以很容易地观察到，对于任何具有奇数和的子数组：
1.  因为只有奇数值会导致奇数和，所以我们可以忽略偶数值。
2.  奇数的数量也必须是奇数。
3.  因此，对于 `K` 个子数组，我们在数组中至少需要 `K` 个奇数值。如果 `K` 大于奇数元素的数量，那么答案总是 `-1`。

以下是上述方法的实现：

## C++

```cpp
// C++ program to split the array into K
// disjoint subarrays so that the sum of
// each subarray is odd.

#include <iostream>
using namespace std;

// Function to split the array into K
// disjoint subarrays so that the sum of
// each subarray is odd.
void split(int a[], int n, int k)
{
    // Number of odd elements
    int odd_ele = 0;

    // Loop to store the number
    // of odd elements in the array
    for (int i = 0; i < n; i++)
        if (a[i] % 2)
            odd_ele++;

    // If the count of odd elements is < K
    // then the answer doesnt exist
    if (odd_ele < k)
        cout << -1;

    // If the number of odd elements is
    // greater than K and the extra
    // odd elements are odd, then the
    // answer doesn't exist
    else if (odd_ele > k && (odd_ele - k) % 2)
        cout << -1;

    else {
        for (int i = 0; i < n; i++) {
            if (a[i] % 2) {

                // Printing the position of
                // odd elements
                cout << i + 1 << " ";

                // Decrementing K as we need positions
                // of only first k odd numbers
                k--;
            }

            // When the positions of the first K
            // odd numbers are printed
            if (k == 0)
                break;
        }
    }
}

// Driver code
int main()
{
    int n = 5;
    int arr[] = { 7, 2, 11, 4, 19 };
    int k = 3;

    split(arr, n, k);
}
```

## Java

```java
// Java program to split the array into K
// disjoint subarrays so that the sum of
// each subarray is odd.
class GFG{

// Function to split the array into K
// disjoint subarrays so that the sum of
// each subarray is odd.
static void split(int a[], int n, int k)
{
    // Number of odd elements
    int odd_ele = 0;

    // Loop to store the number
    // of odd elements in the array
    for (int i = 0; i < n; i++)
        if (a[i] % 2==1)
            odd_ele++;

    // If the count of odd elements is < K
    // then the answer doesnt exist
    if (odd_ele < k)
        System.out.print(-1);

    // If the number of odd elements is
    // greater than K and the extra
    // odd elements are odd, then the
    // answer doesn't exist
    else if (odd_ele > k && (odd_ele - k) % 2==1)
        System.out.print(-1);

    else {
        for (int i = 0; i < n; i++) {
            if (a[i] % 2==1) {

                // Printing the position of
                // odd elements
                System.out.print(i + 1+ " ");

                // Decrementing K as we need positions
                // of only first k odd numbers
                k--;
            }

            // When the positions of the first K
            // odd numbers are printed
            if (k == 0)
                break;
        }
    }
}

// Driver code
public static void main(String[] args)
{
    int n = 5;
    int arr[] = { 7, 2, 11, 4, 19 };
    int k = 3;

    split(arr, n, k);
}
}

// This code is contributed by 29AjayKumar
```

## Python 3

```python
# Python3 program to split the array into K
# disjoint subarrays so that the sum of
# each subarray is odd.

# Function to split the array into K
# disjoint subarrays so that the sum of
# each subarray is odd.
def split(a, n, k) :

    # Number of odd elements
    odd_ele = 0;

    # Loop to store the number
    # of odd elements in the array
    for i in range(n) :
        if (a[i] % 2) :
            odd_ele += 1;

    # If the count of odd elements is < K
    # then the answer doesnt exist
    if (odd_ele < k) :
        print(-1);

    # If the number of odd elements is
    # greater than K and the extra
    # odd elements are odd, then the
    # answer doesn't exist
    elif (odd_ele > k and (odd_ele - k) % 2) :
        print(-1);

    else :
        for i in range(n) :
            if (a[i] % 2) :

                # Printing the position of
                # odd elements
                print(i + 1 ,end= " ");

                # Decrementing K as we need positions
                # of only first k odd numbers
                k -= 1;

            # When the positions of the first K
            # odd numbers are printed
            if (k == 0) :
                break;

# Driver code
if __name__ == "__main__" :

    n = 5;
    arr = [ 7, 2, 11, 4, 19 ];
    k = 3;

    split(arr, n, k);

    # This code is contributed by AnkitRai01
```

## C#

```csharp
// C# program to split the array into K
// disjoint subarrays so that the sum of
// each subarray is odd.
using System;

class GFG{

// Function to split the array into K
// disjoint subarrays so that the sum of
// each subarray is odd.
static void split(int []a, int n, int k)
{
    // Number of odd elements
    int odd_ele = 0;

    // Loop to store the number
    // of odd elements in the array
    for (int i = 0; i < n; i++)
        if (a[i] % 2 == 1)
            odd_ele++;

    // If the count of odd elements is < K
    // then the answer doesnt exist
    if (odd_ele < k)
        Console.Write(-1);

    // If the number of odd elements is
    // greater than K and the extra
    // odd elements are odd, then the
    // answer doesn't exist
    else if (odd_ele > k && (odd_ele - k) % 2 == 1)
        Console.Write(-1);

    else {
        for (int i = 0; i < n; i++) {
            if (a[i] % 2 == 1) {

                // Printing the position of
                // odd elements
                Console.Write(i + 1 + " ");

                // Decrementing K as we need positions
                // of only first k odd numbers
                k--;
            }

            // When the positions of the first K
            // odd numbers are printed
            if (k == 0)
                break;
        }
    }
}

// Driver code
public static void Main(string[] args)
{
    int n = 5;
    int []arr = { 7, 2, 11, 4, 19 };
    int k = 3;

    split(arr, n, k);
}
}

// This code is contributed by AnkitRai01
```

## java 描述语言

```javascript
<script>
// Javascript program to split the array into K
// disjoint subarrays so that the sum of
// each subarray is odd.

// Function to split the array into K
// disjoint subarrays so that the sum of
// each subarray is odd.
function split(a, n, k)
{
    // Number of odd elements
    let odd_ele = 0;

    // Loop to store the number
    // of odd elements in the array
    for (let i = 0; i < n; i++)
        if (a[i] % 2)
            odd_ele++;

    // If the count of odd elements is < K
    // then the answer doesnt exist
    if (odd_ele < k)
        document.write(-1);

    // If the number of odd elements is
    // greater than K and the extra
    // odd elements are odd, then the
    // answer doesn't exist
    else if (odd_ele > k && (odd_ele - k) % 2)
        document.write(1);

    else {
        for (let i = 0; i < n; i++) {
            if (a[i] % 2) {

                // Printing the position of
                // odd elements
                document.write(i + 1 + " ");

                // Decrementing K as we need positions
                // of only first k odd numbers
                k--;
            }

            // When the positions of the first K
            // odd numbers are printed
            if (k == 0)
                break;
        }
    }
}

// Driver code

let n = 5;
let arr = [ 7, 2, 11, 4, 19 ];
let k = 3;

split(arr, n, k);

// This code is contributed by gfgking
</script>
```

Output:

```text
1 3 5
```

时间复杂度: `O(N)`