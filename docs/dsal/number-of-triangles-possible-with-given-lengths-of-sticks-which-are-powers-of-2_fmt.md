# 给定长度的棒的 2 的幂的可能三角形的数量

> 原文: [https://www.geeksforgeeks.org/number-of-triangles-possible-with-given-lengths-of-sticks-which-are-powers-of-2/](https://www.geeksforgeeks.org/number-of-triangles-possible-with-given-lengths-of-sticks-which-are-powers-of-2/)

给定一组 `N` 个整数，其中 `arr[i]` 表示长度为 `2^i` 的木棒数量。任务是找出给定长度下面积 `≥ 0` 的三角形的可能数量。
注：每根木棍只能使用一次。

**示例：**

> **输入：** `a[] = {1, 2, 2, 2, 2}`
> **输出：** 3
> 所有可能的三角形为：
> `(2^0, 2^4, 2^4)`、`(2^1, 2^3, 2^3)`、`(2^1, 2^2, 2^2)`

> **输入：** `a[] = {3, 3, 3}`
> **输出：** 3

**逼近：** 主要观察的是面积 `≥ 0` 的三角形只有当有三根相同长度的木棒或一根不同长度的木棒和两根相似长度的木棒时才能形成。因此贪婪地从后面迭代，计算可用的相同长度的木棒对的数量，即 `arr[i]/2`。但是如果还剩下一根棍子，那么就用一对和一根棍子组成一个三角形。最后算出剩下的木棒总数为 `2 * pairs`，这些剩余的木棒可以形成的三角形数量为 `(2 * pairs) / 3`。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the
// number of positive area triangles
int countTriangles(int a[], int n)
{

    // To store the count of
    // total triangles
    int cnt = 0;

    // To store the count of pairs of sticks
    // with equal lengths
    int pairs = 0;

    // Back-traverse and count
    // the number of triangles
    for (int i = n - 1; i >= 0; i--) {

        // Count the number of pairs
        pairs += a[i] / 2;

        // If we have one remaining stick
        // and we have a pair
        if (a[i] % 2 == 1 && pairs > 0) {

            // Count 1 triangle
            cnt += 1;

            // Reduce one pair
            pairs -= 1;
        }
    }

    // Count the remaining triangles
    // that can be formed
    cnt += (2 * pairs) / 3;
    return cnt;
}

// Driver code
int main()
{
    int a[] = { 1, 2, 2, 2, 2 };
    int n = sizeof(a) / sizeof(a[0]);
    cout << countTriangles(a, n);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG
{

// Function to return the
// number of positive area triangles
static int countTriangles(int a[], int n)
{

    // To store the count of
    // total triangles
    int cnt = 0;

    // To store the count of pairs of sticks
    // with equal lengths
    int pairs = 0;

    // Back-traverse and count
    // the number of triangles
    for (int i = n - 1; i >= 0; i--)
    {

        // Count the number of pairs
        pairs += a[i] / 2;

        // If we have one remaining stick
        // and we have a pair
        if (a[i] % 2 == 1 && pairs > 0)
        {

            // Count 1 triangle
            cnt += 1;

            // Reduce one pair
            pairs -= 1;
        }
    }

    // Count the remaining triangles
    // that can be formed
    cnt += (2 * pairs) / 3;
    return cnt;
}

// Driver code
public static void main(String[] args)
{
    int a[] = { 1, 2, 2, 2, 2 };
    int n = a.length;
    System.out.println(countTriangles(a, n));
}
}

// This code is contributed by Code_Mech.
```

## Python 3

```python
# Python3 implementation of the approach

# Function to return the
# number of positive area triangles
def countTriangles(a, n):

    # To store the count of
    # total triangles
    cnt = 0

    # To store the count of pairs of sticks
    # with equal lengths
    pairs = 0

    # Back-traverse and count
    # the number of triangles
    for i in range(n - 1, -1, -1):

        # Count the number of pairs
        pairs += a[i] // 2

        # If we have one remaining stick
        # and we have a pair
        if (a[i] % 2 == 1 and pairs > 0):

            # Count 1 triangle
            cnt += 1

            # Reduce one pair
            pairs -= 1

    # Count the remaining triangles
    # that can be formed
    cnt += (2 * pairs) // 3
    return cnt

# Driver code
a = [1, 2, 2, 2, 2]
n = len(a)
print(countTriangles(a, n))

# This code is contributed by mohit kumar
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

    // Function to return the
    // number of positive area triangles
    static int countTriangles(int []a, int n)
    {

        // To store the count of
        // total triangles
        int cnt = 0;

        // To store the count of pairs of sticks
        // with equal lengths
        int pairs = 0;

        // Back-traverse and count
        // the number of triangles
        for (int i = n - 1; i >= 0; i--)
        {

            // Count the number of pairs
            pairs += a[i] / 2;

            // If we have one remaining stick
            // and we have a pair
            if (a[i] % 2 == 1 && pairs > 0)
            {

                // Count 1 triangle
                cnt += 1;

                // Reduce one pair
                pairs -= 1;
            }
        }

        // Count the remaining triangles
        // that can be formed
        cnt += (2 * pairs) / 3;
        return cnt;
    }

    // Driver code
    public static void Main()
    {
        int []a = { 1, 2, 2, 2, 2 };
        int n = a.Length;
        Console.WriteLine(countTriangles(a, n));
    }
}

// This code is contributed by Ryuga
```

## PHP

```php
<?php
// PHP implementation of the approach

// Function to return the
// number of positive area triangles
Function countTriangles($a, $n)
{

    // To store the count of
    // total triangles
    $cnt = 0;

    // To store the count of pairs of sticks
    // with equal lengths
    $pairs = 0;

    // Back-traverse and count
    // the number of triangles
    for ($i = $n - 1; $i >= 0; $i--)
    {

        // Count the number of pairs
        $pairs += $a[$i] / 2;

        // If we have one remaining stick
        // and we have a pair
        if ($a[$i] % 2 == 1 && $pairs > 0)
        {

            // Count 1 triangle
            $cnt += 1;

            // Reduce one pair
            $pairs -= 1;
        }
    }

    // Count the remaining triangles
    // that can be formed
    $cnt += (int)((2 * $pairs) / 3);
    return $cnt;
}

// Driver code
$a = array(1, 2, 2, 2, 2 );
$n = sizeof($a);
echo(countTriangles($a, $n));

// This code is contributed by Code_Mech.
?>
```

## JavaScript

```javascript
<script>

// Javascript implementation of the approach

// Function to return the number
// of positive area triangles
function countTriangles(a , n)
{

    // To store the count of
    // total triangles
    var cnt = 0;

    // To store the count of pairs
    // of sticks with equal lengths
    var pairs = 0;

    // Back-traverse and count
    // the number of triangles
    for(let i = n - 1; i >= 0; i--)
    {

        // Count the number of pairs
        pairs += a[i] / 2;

        // If we have one remaining stick
        // and we have a pair
        if (a[i] % 2 == 1 && pairs > 0)
        {

            // Count 1 triangle
            cnt += 1;

            // Reduce one pair
            pairs -= 1;
        }
    }

    // Count the remaining triangles
    // that can be formed
    cnt += parseInt((2 * pairs) / 3);
    return cnt;
}

// Driver code
var a = [ 1, 2, 2, 2, 2 ];
var n = a.length;

document.write(countTriangles(a, n));

// This code is contributed by aashish1995

</script>
```

**Output：**

```