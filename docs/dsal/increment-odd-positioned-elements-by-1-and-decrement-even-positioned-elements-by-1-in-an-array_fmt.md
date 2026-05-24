# 数组中奇数位置的元素增加 1，偶数位置的元素减少 1

> 原文：[https://www.geeksforgeeks.org/increment-odd-positioned-elements-by-1-and-decrement-even-positioned-elements-by-1-in-an-array/](https://www.geeksforgeeks.org/increment-odd-positioned-elements-by-1-and-decrement-even-positioned-elements-by-1-in-an-array/)

给定一个数组 `arr[]`，任务是将所有**奇数定位元素**递增 `1`，将所有**偶数定位元素**递减 `1`。

**示例:**

> **输入:** `arr[] = {3，6，8}`
> **输出:** `4 5 9`
>
> **输入:** `arr[] = {9，7，3}`
> **输出:** `10 6 4`

## 方法

逐元素遍历数组元素，如果当前元素的位置是奇数，则递增 1，否则递减 1。最后打印更新后数组的内容。

下面是上述方法的实现:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Utility function to print
// the contents of an array
void printArr(int arr[], int n)
{
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
}

// Function to increment all the odd
// positioned elements by 1 and decrement
// all the even positioned elements by 1
void updateArr(int arr[], int n)
{
    for (int i = 0; i < n; i++)

        // If current element is odd positioned
        if ((i + 1) % 2 == 1)
            arr[i]++;

        // If even positioned
        else
            arr[i]--;

    // Print the updated array
    printArr(arr, n);
}

// Driver code
int main()
{
    int arr[] = { 3, 6, 8 };
    int n = sizeof(arr) / sizeof(arr[0]);
    updateArr(arr, n);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GfG
{

// Utility function to print
// the contents of an array
static void printArr(int arr[], int n)
{
    for (int i = 0; i < n; i++)
        System.out.print(arr[i] + " ");
}

// Function to increment all the odd
// positioned elements by 1 and decrement
// all the even positioned elements by 1
static void updateArr(int arr[], int n)
{
    for (int i = 0; i < n; i++)

        // If current element is odd positioned
        if ((i + 1) % 2 == 1)
            arr[i]++;

        // If even positioned
        else
            arr[i]--;

    // Print the updated array
    printArr(arr, n);
}

// Driver code
public static void main(String[] args)
{
    int arr[] = { 3, 6, 8 };
    int n = arr.length;
    updateArr(arr, n);

}
}

// This code is contributed by Prerna Saini
```

## Python 3

```python
# Python3 implementation of the approach

# Utility function to print
# the contents of an array
def printArr(arr, n):
    for i in range(0, n):
        print(arr[i], end = " ");

# Function to increment all the odd
# positioned elements by 1 and decrement
# all the even positioned elements by 1
def updateArr(arr, n):
    for i in range(0, n):

        # If current element is odd positioned
        if ((i + 1) % 2 == 1):
            arr[i] += 1;

        # If even positioned
        else:
            arr[i] -= 1;

    # Print the updated array
    printArr(arr, n);

# Driver code
if __name__ == '__main__':
    arr = [3, 6, 8];
    n = len(arr);
    updateArr(arr, n);

# This code contributed by PrinciRaj1992
```

## C#

```csharp
// C# implementation of the approach
class GfG
{

// Utility function to print
// the contents of an array
static void printArr(int []arr, int n)
{
    for (int i = 0; i < n; i++)
        System.Console.Write(arr[i] + " ");
}

// Function to increment all the odd
// positioned elements by 1 and decrement
// all the even positioned elements by 1
static void updateArr(int []arr, int n)
{
    for (int i = 0; i < n; i++)

        // If current element is odd positioned
        if ((i + 1) % 2 == 1)
            arr[i]++;

        // If even positioned
        else
            arr[i]--;

    // Print the updated array
    printArr(arr, n);
}

// Driver code
static void Main()
{
    int []arr = { 3, 6, 8 };
    int n = arr.Length;
    updateArr(arr, n);

}
}

// This code is contributed by mits
```

## PHP

```php
<?php
// PHP implementation of the approach

// Utility function to print
// the contents of an array
function printArr($arr, $n)
{
    for ($i = 0; $i < $n; $i++)
        echo $arr[$i] . " ";
}

// Function to increment all the odd
// positioned elements by 1 and decrement
// all the even positioned elements by 1
function updateArr($arr, $n)
{
    for ($i = 0; $i < $n; $i++)

        // If current element is odd positioned
        if (($i + 1) % 2 == 1)
            $arr[$i]++;

        // If even positioned
        else
            $arr[$i]--;

    // Print the updated array
    printArr($arr, $n);
}

// Driver code
$arr = array( 3, 6, 8 );
$n = count($arr);
updateArr($arr, $n);

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>

// javascript implementation of the approach

// Utility function to print
// the contents of an array
function printArr(arr, n)
{
     var i;
    for (i = 0; i < n; i++)
      document.write(arr[i] + " ");
}

// Function to increment all the odd
// positioned elements by 1 and decrement
// all the even positioned elements by 1
function updateArr(arr, n)
{
    var i;
    for (i = 0; i < n; i++)

        // If current element is odd positioned
        if ((i + 1) % 2 == 1)
            arr[i]++;

        // If even positioned
        else
            arr[i]--;

    // Print the updated array
    printArr(arr, n);
}

// Driver code
    var arr = [3, 6, 8];
    var n = arr.length;
    updateArr(arr, n);

</script>
```

**Output:**

```
4 5 9
```

**时间复杂度:** `O(n)`

**辅助空间:** `O(1)`