# 统计数字线上访问的不同点

> 原文：[https://www.geeksforgeeks.org/count-distinct-points-visited-on-the-number-line/](https://www.geeksforgeeks.org/count-distinct-points-visited-on-the-number-line/)

给定一个位于位置 `current_pos` 的人和一个二进制字符串 `path`，这是这个人采取的移动。如果 `path[i] = '0'`，那么这个人向左移动一步；如果 `path[i] = '1'`，那么这个人向右移动一步。任务是找到这个人拜访过的不同位置的数量。

**示例：**

> **输入：** `current_pos = 5`，`path = "011101"`
> **输出：** 4
> 给定的招式有左、右、右、右、左、右
> 即 5->4->5->6->7->6->7
> 不同的位置数为 4 (4、5、6、7)。
>
> **输入：** `current_pos = 3`，`path = "110100"`
> **输出：** 3
> 3->4->5->4->5->4->3

## 进场思路

*   声明一个数组 `points[]` 来存储这个人经历的所有点。
*   将该数组的第一个位置初始化为当前位置 `current_pos`。
*   遍历字符串 `path` 并执行以下操作：
    *   如果当前字符是 `'0'`，则此人向左行进。所以将当前位置减 `1` 存储在 `points[]`。
    *   如果当前字符是 `'1'`，那么此人向右行进。所以将当前位置增加 `1` 存储在 `points[]`。
*   计算 `points[]` 中不同元素的总数。参考[计算数组中不同元素的数量](https://www.geeksforgeeks.org/count-distinct-elements-in-an-array/)了解计算数组中不同元素数量的不同方法。

下面是上述方法的实现：

## C++ 实现

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Utility function to return the number
// of distinct elements in an array
int countDistinct(int arr[], int len)
{

    set<int> hs;

    for (int i = 0; i < len; i++) {
        // add all the elements to the HashSet
        hs.insert(arr[i]);
    }

    // Return the size of hashset as
    // it consists of all unique elements
    return hs.size();
}

// Function to return the count of
// positions the person went to
int getDistinctPoints(int current_pos, string path)
{

    // Length of path
    int len = path.length();

    // Array to store all the points traveled
    int points[len + 1];

    // The first point is the current_pos
    points[0] = current_pos;

    // For all the directions in path
    for (int i = 0; i < len; i++) {

        // Get whether the direction was left or right
        char ch = path[i];

        // If the direction is left
        if (ch == '0') {

            // Decrement the current position by 1
            current_pos--;

            // Store the current position in array
            points[i + 1] = current_pos;
        }

        // If the direction is right
        else {

            // Increment the current position by 1
            current_pos++;

            // Store the current position in array
            points[i + 1] = current_pos;
        }
    }

    return countDistinct(points, len + 1);
}

// Driver code
int main()
{
    int current_pos = 5;
    string path = "011101";

    cout << (getDistinctPoints(current_pos, path));

    return 0;
}
// contributed by Arnab Kundu
```

## Java 实现

```java
// Java implementation of the approach
import java.util.*;
class GFG {

    // Function to return the count of
    // positions the person went to
    public static int getDistinctPoints(int current_pos, String path)
    {

        // Length of path
        int len = path.length();

        // Array to store all the points traveled
        int points[] = new int[len + 1];

        // The first point is the current_pos
        points[0] = current_pos;

        // For all the directions in path
        for (int i = 0; i < len; i++) {

            // Get whether the direction was left or right
            char ch = path.charAt(i);

            // If the direction is left
            if (ch == '0') {

                // Decrement the current position by 1
                current_pos--;

                // Store the current position in array
                points[i + 1] = current_pos;
            }

            // If the direction is right
            else {

                // Increment the current position by 1
                current_pos++;

                // Store the current position in array
                points[i + 1] = current_pos;
            }
        }

        return countDistinct(points, len + 1);
    }

    // Utility function to return the number
    // of distinct elements in an array
    public static int countDistinct(int arr[], int len)
    {

        HashSet<Integer> hs = new HashSet<Integer>();

        for (int i = 0; i < len; i++) {
            // add all the elements to the HashSet
            hs.add(arr[i]);
        }

        // Return the size of hashset as
        // it consists of all unique elements
        return hs.size();
    }

    // Driver code
    public static void main(String[] args)
    {
        int current_pos = 5;
        String path = "011101";

        System.out.print(getDistinctPoints(current_pos, path));
    }
}
```

## Python 3 实现

```python
# Utility function to return the number
# of distinct elements in an array
def countDistinct(arr, Len):

    hs = dict()

    for i in range(Len):

        # add all the elements to the HashSet
        hs[arr[i]] = 1

    # Return the size of hashset as
    # it consists of all unique elements
    return len(hs)

# Function to return the count of
# positions the person went to
def getDistinctPoints(current_pos, path):

    # Length of path
    Len = len(path)

    # Array to store all the points traveled
    points = [0 for i in range(Len + 1)]

    # The first point is the current_pos
    points[0] = current_pos

    # For all the directions in path
    for i in range(Len):

        # Get whether the direction
        # was left or right
        ch = path[i]

        # If the direction is left
        if (ch == '0'):

            # Decrement the current position by 1
            current_pos -= 1

            # Store the current position in array
            points[i + 1] = current_pos

        # If the direction is right
        else:

            # Increment the current position by 1
            current_pos += 1

            # Store the current position in array
            points[i + 1] = current_pos

    return countDistinct(points, Len + 1)

# Driver code
current_pos = 5
path = "011101"

print(getDistinctPoints(current_pos, path))

# This code is contributed by mohit kumar
```

## C# 实现

```csharp
// C# implementation of the approach
using System;
using System.Collections.Generic;

class GFG {

    // Function to return the count of
    // positions the person went to
    public static int getDistinctPoints(int current_pos,
                                        string path)
    {

        // Length of path
        int len = path.Length;

        // Array to store all the points traveled
        int[] points = new int[len + 1];

        // The first point is the current_pos
        points[0] = current_pos;

        // For all the directions in path
        for (int i = 0; i < len; i++) {

            // Get whether the direction was left or right
            char ch = path[i];

            // If the direction is left
            if (ch == '0') {

                // Decrement the current position by 1
                current_pos--;

                // Store the current position in array
                points[i + 1] = current_pos;
            }

            // If the direction is right
            else {

                // Increment the current position by 1
                current_pos++;

                // Store the current position in array
                points[i + 1] = current_pos;
            }
        }

        return countDistinct(points, len + 1);
    }

    // Utility function to return the number
    // of distinct elements in an array
    public static int countDistinct(int[] arr, int len)
    {

        HashSet<int> hs = new HashSet<int>();

        for (int i = 0; i < len; i++) {
            // add all the elements to the HashSet
            hs.Add(arr[i]);
        }

        // Return the size of hashset as
        // it consists of all unique elements
        return hs.Count;
    }

    // Driver code
    public static void Main(string[] args)
    {
        int current_pos = 5;
        string path = "011101";

        Console.Write(getDistinctPoints(current_pos, path));
    }
}

// This code is contributed by shrikanth13
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
<?php
// PHP implementation of the approach

// Utility function to return the number
// of distinct elements in an array
function countDistinct($arr, $len)
{ 
    $hs = array();

    for ($i = 0; $i < $len; $i++)
    {
        // add all the elements to the HashSet
        array_push($hs, $arr[$i]);
    }

    $hs = array_unique($hs);

    // Return the size of hashset as
    // it consists of all unique elements
    return count($hs);
}

// Function to return the count of
// positions the person went to
function getDistinctPoints($current_pos, $path)
{

    // Length of path
    $len = strlen($path);

    // Array to store all the points traveled
    $points = array();

    // The first point is the current_pos
    $points[0] = $current_pos;

    // For all the directions in path
    for ($i = 0; $i < $len; $i++)
    {

        // Get whether the direction was left or right
        $ch = $path[$i];

        // If the direction is left
        if ($ch == '0')
        {

            // Decrement the current position by 1
            $current_pos--;

            // Store the current position in array
            $points[$i + 1] = $current_pos;
        }

        // If the direction is right
        else
        {

            // Increment the current position by 1
            $current_pos++;

            // Store the current position in array
            $points[$i + 1] = $current_pos;
        }
    }

    return countDistinct($points, $len + 1);
}

// Driver code
$current_pos = 5;
$path = "011101";

echo getDistinctPoints($current_pos, $path);

// This code is contributed by Ryuga
?>
```

## java 描述语言

```javascript
<script>

// JavaScript implementation of the approach

    // Function to return the count of
    // positions the person went to
    function getDistinctPoints(current_pos, path)
    {

        // Length of path
        let len = path.length;

        // Array to store all the points traveled
        let points =
        Array.from({length: len + 1}, (_, i) => 0);

        // The first point is the current_pos
        points[0] = current_pos;

        // For all the directions in path
        for (let i = 0; i < len; i++) {

            // Get whether the direction was left or right
            let ch = path[i];

            // If the direction is left
            if (ch == '0') {

                // Decrement the current position by 1
                current_pos--;

                // Store the current position in array
                points[i + 1] = current_pos;
            }

            // If the direction is right
            else {

                // Increment the current position by 1
                current_pos++;

                // Store the current position in array
                points[i + 1] = current_pos;
            }
        }

        return countDistinct(points, len + 1);
    }

    // Utility function to return the number
    // of distinct elements in an array
    function countDistinct(arr, len)
    {

       let hs = new Set();

        for (let i = 0; i < len; i++) {
            // add all the elements to the HashSet
            hs.add(arr[i]);
        }

        // Return the size of hashset as
        // it consists of all unique elements
        return hs.size;
    }

    // Driver code

    let current_pos = 5;
        let path = "011101";

       document.write(getDistinctPoints(current_pos, path));

</script>
```

**Output:**

```output

```