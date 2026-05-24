# 查找排序数组中唯一缺失的数字

> 原文：[https://www.geeksforgeeks.org/find-the-only-missing-number-in-a-sorted-array/](https://www.geeksforgeeks.org/find-the-only-missing-number-in-a-sorted-array/)

给你一个从 1 到 N 的 N 个整数的排序数组，其中缺少一个数字。查找缺少的数字，预计时间复杂度为 `O(logn)`。

## 示例

```
Input : ar[] = {1, 3, 4, 5}
Output : 2

Input : ar[] = {1, 2, 3, 4, 5, 7, 8}
Output : 6
```

一个简单的解决方案是线性遍历给定的数组。找到当前元素不比先前元素多一个的点。

一个高效的解决方案就是使用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)。我们使用索引来搜索丢失的元素并修改二分搜索法。如果 `ar[mid] != mid+1`，这是第一个缺少的元素，然后 `mid + 1` 是缺少的元素。否则，如果这不是第一个缺少的元素，而是 `ar[mid] != mid+1`，在左半部分搜索。否则搜索右半部分，如果 `l > r`，则没有元素丢失。

## C++

```cpp
// CPP program to find the only missing element.
#include <iostream>
using namespace std;

int findmissing(int ar[], int N)
{
    int l = 0, r = N - 1;
    while (l <= r) {

        int mid = (l + r) / 2;

        // If this is the first element
        // which is not index + 1, then
        // missing element is mid+1
        if (ar[mid] != mid + 1 &&
                        ar[mid - 1] == mid)
            return mid + 1;

        // if this is not the first missing
        // element search in left side
        if (ar[mid] != mid + 1)
            r = mid - 1;

        // if it follows index+1 property then
        // search in right side
        else
            l = mid + 1;
    }

    // if no element is missing
    return -1;
}

// Driver code
int main()
{
    int arr[] = {1, 2, 3, 4, 5, 7, 8};
    int N = sizeof(arr)/sizeof(arr[0]);
    cout << findmissing(arr, N);
    return 0;
}
```

## Java

```java
// Java program to find
// the only missing element.
class GFG
{
static int findmissing(int [] ar, int N)
{

    int l = 0, r = N - 1;
    while (l <= r)
    {
        int mid = (l + r) / 2;

        // If this is the first element
        // which is not index + 1, then
        // missing element is mid+1
        if (ar[mid] != mid + 1 &&
            ar[mid - 1] == mid)
            return (mid + 1);

        // if this is not the first
        // missing element search
        // in left side
        if (ar[mid] != mid + 1)
            r = mid - 1;

        // if it follows index+1
        // property then search
        // in right side
        else
            l = mid + 1;
    }

// if no element is missing
return -1;
}

// Driver code
public static void main(String [] args)
{
    int arr[] = {1, 2, 3, 4, 5, 7, 8};
    int N = arr.length;
    System.out.println(findmissing(arr, N));
}
}

// This code is contributed
// by Shivi_Aggarwal
```

## Python 3

```python
# PYTHON 3 program to find
# the only missing element.
def findmissing(ar, N):
    l = 0
    r = N - 1
    while (l <= r):
        mid = (l + r) / 2
        mid = int(mid)

    # If this is the first element
    # which is not index + 1, then
    # missing element is mid+1
        if(ar[mid] != mid + 1 and
           ar[mid - 1] == mid):
            return (mid + 1)

    # if this is not the first
    # missing element search
    # in left side
        elif(ar[mid] != mid + 1):
            r = mid - 1

    # if it follows index+1
    # property then search
    # in right side
        else:
            l = mid + 1

    # if no element is missing
    return (-1)

def main():
    ar = [1, 2, 3, 4, 5, 7, 8]
    N = len(ar)
    res = findmissing(ar, N)
    print(res)
if __name__ == "__main__":
    main()

# This code is contributed
# by Shivi_Aggarwal
```

## C#

```csharp
// C# program to find
// the only missing element.
using System;

class GFG
{
static int findmissing(int []ar,
                       int N)
{

    int l = 0, r = N - 1;
    while (l <= r)
    {
        int mid = (l + r) / 2;

        // If this is the first element
        // which is not index + 1, then
        // missing element is mid+1
        if (ar[mid] != mid + 1 &&
            ar[mid - 1] == mid)
            return (mid + 1);

        // if this is not the first
        // missing element search
        // in left side
        if (ar[mid] != mid + 1)
            r = mid - 1;

        // if it follows index+1
        // property then search
        // in right side
        else
            l = mid + 1;
    }

// if no element is missing
return -1;
}

// Driver code
public static void Main()
{
    int []arr = {1, 2, 3, 4, 5, 7, 8};
    int N = arr.Length;
    Console.WriteLine(findmissing(arr, N));
}
}

// This code is contributed
// by Akanksha Rai(Abby_akku)
```

## PHP

```php
<?php
// PHP program to find
// the only missing element.
function findmissing(&$ar, $N)
{
    $r = $N - 1;
    $l = 0;
    while ($l <= $r)
    {
        $mid = ($l + $r) / 2;

        // If this is the first element
        // which is not index + 1, then
        // missing element is mid+1
        if ($ar[$mid] != $mid + 1 &&
            $ar[$mid - 1] == $mid)
            return ($mid + 1);

        // if this is not the first
        // missing element search
        // in left side
        if ($ar[$mid] != $mid + 1)
            $r = $mid - 1;

        // if it follows index+1
        // property then search
        // in right side
        else
            $l = $mid + 1;
    }

    // if no element is missing
    return (-1);
}

// Driver Code
$ar = array(1, 2, 3, 4, 5, 7, 8);
$N = sizeof($ar);
echo(findmissing($ar, $N));

// This code is contributed
// by Shivi_Aggarwal
?>
```

## JavaScript

```javascript
<script>
// JavaScript program to find the only missing element.

function findmissing(ar, N) {
    var l = 0,
        r = N - 1;
    while (l <= r) {
        var mid = parseInt((l + r) / 2);

        // If this is the first element
        // which is not index + 1, then
        // missing element is mid+1
        if (ar[mid] != mid + 1 && ar[mid - 1] == mid)
            return mid + 1;

        // if this is not the first missing
        // element search in left side
        if (ar[mid] != mid + 1) r = mid - 1;
        // if it follows index+1 property then
        // search in right side
        else l = mid + 1;
    }

    // if no element is missing
    return -1;
}

// Driver code
var arr = [1, 2, 3, 4, 5, 7, 8];
var N = arr.length;
document.write(findmissing(arr, N));
</script>
```

**输出：**

```
6
```

**时间复杂度：** `O(Log n)`
**辅助空间：** `O(1)`