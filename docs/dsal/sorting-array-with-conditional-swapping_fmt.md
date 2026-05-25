# 带条件交换的排序数组

> 原文：[https://www.geeksforgeeks.org/sorting-array-with-conditional-swapping/](https://www.geeksforgeeks.org/sorting-array-with-conditional-swapping/)

给定一个数组 `arr`，其中包含来自 `[1...n]` 的元素。每个元素在数组 `arr` 中只出现一次。给定一根长度为 `n-1` 的字符串 `str`。字符串的每个字符都是 `'0'` 或 `'1'`。在数组中，将第 `i` 个元素与第 `(i + 1)` 个元素进行交换可以任意多次，如果字符串的第 `i` 个字符为 `'1'`。我们的任务是找出是否有可能按升序对数组进行排序。

**举例：**

```
Input : arr = {1, 2, 5, 3, 4, 6}
        str = "01110"
Output : Yes
Explanation :
Here, we can swap arr[2] and arr[3], and then 
swap arr[3] and arr[4].

Input : arr = {1, 2, 5, 3, 4, 6}
        str = "01010"
Output : No
Explanation :
Here, the 3rd element of the array i.e. 5 can not
be swapped as the 3rd character of the string is 0. 
Therefore it is impossible to sort the array.
```

**方法：** 对字符串 `str` 的长度进行循环，并为每个 `i` 计算从 `0` 到 `i` 的数组的 `max_element`。在每次迭代时，如果字符串的第 `i` 个字符为 `'0'`，且 `max_element` 大于 `i + 1`，则不可能对数组进行排序，否则，可能。

基本执行上述办法：

## C++

```cpp
// CPP program to Check if it
// is possible to sort the
// array in ascending order.
#include <bits/stdc++.h>
using namespace std;

// Function to check if it is possible to
// sort the array
string possibleToSort(int* arr, int n, string str)
{
    int max_element = -1;
    for (long i = 0; i < str.size(); i++) {

        // Calculating max_element
        // at each iteration.
        max_element = max(max_element, arr[i]);

        // if we can not swap the i-th element.
        if (str[i] == '0') {

            // if it is impossible to swap the
            // max_element then we can not
            // sort the array.
            if (max_element > i + 1)
                return "No";
        }
    }

    // Otherwise, we can sort the array.
    return "Yes";
}

// Driver function
int main()
{
    int arr[] = { 1, 2, 5, 3, 4, 6 };
    int n = sizeof(arr) / sizeof(arr[0]);
    string str = "01110";
    cout << possibleToSort(arr, n, str);
    return 0;
}
```

## Java

```java
// Java program to Check if it is possible to
// sort the array in ascending order.
import java.util.*;
import java.lang.*;

// Function to check if it is possible to
// sort the array
class GFG
{

    public static String possibleToSort(int arr[],
                                int n, String str)
    {

        int max_element = -1;
        for (int i = 0; i < str.length(); i++)
        {

            // Calculating max_element at each
            // iteration.
            max_element = Math.max(max_element,
                                       arr[i]);

            // if we can not swap the i-th
            // element.
            if (str.charAt(i) == '0') {

                // if it is impossible to swap
                // the max_element then we can
                // not sort the array.
                if (max_element > i + 1)
                    return "No";
            }
        }

        // Otherwise, we can sort the array.
        return "Yes";

    }

    // Driven Program
    public static void main(String[] args)
    {
        int arr[] = { 1, 2, 5, 3, 4, 6 };
        int n = arr.length;
        String str = "01110";
        System.out.println(
             possibleToSort(arr, n, str));
    }
}

// This code is contributed by Prasad Kshirsagar
```

## Python 3

```python
# Python 3 program to Check if it
# is possible to sort the
# array in ascending order.

# Function to check if it is
# possible to sort the array
def possibleToSort(arr, n, str):

    max_element = -1
    for i in range(len(str)) :

        # Calculating max_element
        # at each iteration.
        max_element = max(max_element, arr[i])

        # if we can not swap the i-th element.
        if (str[i] == '0') :

            # if it is impossible to swap the
            # max_element then we can not
            # sort the array.
            if (max_element > i + 1):
                return "No"

    # Otherwise, we can sort the array.
    return "Yes"

# Driver Code
if __name__ == "__main__":

    arr = [ 1, 2, 5, 3, 4, 6 ]
    n = len(arr)
    str = "01110"
    print(possibleToSort(arr, n, str))

# This code is contributed
# by ChitraNayal
```

## C#

```csharp
// C# program to Check if it
// is possible to sort the
// array in ascending order
using System;
class GFG {

// Function to check if it
// is possible to sort the array
static string possibleToSort(int []arr,
                             int n,
                             string str)
{
    int max_element = -1;
    for (int i = 0; i < str.Length; i++)
    {

        // Calculating max_element
        // at each iteration.
        max_element = Math.Max(max_element,
                                   arr[i]);

        // if we can not swap
        // the i-th element.
        if (str[i] == '0')
        {

            // if it is impossible to swap the
            // max_element then we can not
            // sort the array.
            if (max_element > i + 1)
                return "No";
        }
    }

    // Otherwise, we can
    // sort the array.
    return "Yes";
}

    // Driver Code
    static public void Main ()
    {
        int []arr = {1, 2, 5, 3, 4, 6};
        int n = arr.Length;
        string str = "01110";
        Console.WriteLine(possibleToSort(arr, n, str));
    }
}

// This code is contributed by anuj_67.
```

## PHP

```php
<?php
// PHP program to Check if it is possible
// to sort the array in ascending order.

// Function to check if it is possible
// to sort the array
function possibleToSort($arr, $n, $str)
{
    $max_element = -1;
    for ($i = 0; $i < sizeof($str); $i++)
    {

        // Calculating max_element
        // at each iteration.
        $max_element = max($max_element,
                           $arr[$i]);

        // if we can not swap the i-th element.
        if ($str[$i] == '0')
        {

            // if it is impossible to swap the
            // max_element then we can not
            // sort the array.
            if ($max_element > $i + 1)
                return "No";
        }
    }

    // Otherwise, we can sort the array.
    return "Yes";
}

// Driver Code
$arr = array(1, 2, 5, 3, 4, 6);
$n = sizeof($arr);
$str = "01110";
echo possibleToSort($arr, $n, $str);

// This code is contributed
// by Akanksha Rai
?>
```

## JavaScript

```javascript
<script>
    // Javascript program to Check if it
    // is possible to sort the
    // array in ascending order

    // Function to check if it
    // is possible to sort the array
    function possibleToSort(arr, n, str)
    {
        let max_element = -1;
        for (let i = 0; i < str.length; i++)
        {

            // Calculating max_element
            // at each iteration.
            max_element = Math.max(max_element, arr[i]);

            // if we can not swap
            // the i-th element.
            if (str[i] == '0')
            {

                // if it is impossible to swap the
                // max_element then we can not
                // sort the array.
                if (max_element > i + 1)
                    return "No";
            }
        }

        // Otherwise, we can
        // sort the array.
        return "Yes";
    }

    let arr = [1, 2, 5, 3, 4, 6];
    let n = arr.length;
    let str = "01110";
    document.write(possibleToSort(arr, n, str));

    // This code is contributed by divyesh072019.
</script>
```

**Output：**

```
Yes
```