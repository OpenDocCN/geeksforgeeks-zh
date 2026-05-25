# 每个元素的和提升到(质数-1) %质数

> 原文：[https://www.geeksforgeeks.org/sum-of-each-element-raised-to-prime-1-prime/](https://www.geeksforgeeks.org/sum-of-each-element-raised-to-prime-1-prime/)

给定一个数组`arr[]`和一个正整数`P`，其中`P`是**素数**，数组中的非元素可被`P`整除。求数组中所有上升到幂的元素的和`P–1`即`arr[0]<sup>P–1</sup>+arr[1]<sup>P–1</sup>+…+arr[n–1]<sup>P–1</sup>`并打印结果模`P`。

**举例：**

> **输入：** `arr[] = {2，5}`，`P = 3`
> **输出：** 2
> `2<sup>2</sup>+5<sup>2</sup>= 29` 和 `29 % 3 = 2`
> **输入：** `arr[] = {5，6，8}`，`P = 7`
> **输出：** 3

**方法：** 这个问题是[费马小定理](https://en.wikipedia.org/wiki/Fermat%27s_little_theorem)、`a <sup>(P-1)</sup> = 1 (mod p)`的直接应用，其中`a`不能被`P`整除。由于数组`arr[]`的非元素可被`P`整除，因此每个元素`arr[i]`将通过给定的运算给出值`1`。
因此，我们的答案将是`1+1+……(厄普顿(数组大小))= n`。
以下是上述方法的实施：

## C++

```cpp
// C++ implementation of the approach
#include <iostream>
#include <vector>

using namespace std;

// Function to return the required sum
int getSum(vector<int> arr, int p)
{
    return arr.size();
}

// Driver code
int main()
{
    vector<int> arr = { 5, 6, 8 };
    int p = 7;
    cout << getSum(arr, p) << endl;

    return 0;
}

// This code is contributed by Rituraj Jain
```

## Java

```java
// Java implementation of the approach
public class GFG {

    // Function to return the required sum
    public static int getSum(int arr[], int p)
    {
        return arr.length;
    }

    // Driver code
    public static void main(String[] args)
    {
        int arr[] = { 5, 6, 8 };
        int p = 7;
        System.out.print(getSum(arr, p));
    }
}
```

## Python 3

```python
# Python3 implementation of the approach
# Function to return the required sum
def getSum(arr, p) :

    return len(arr)

# Driver code
if __name__ == "__main__" :

    arr = [5, 6, 8]
    p = 7
    print(getSum(arr, p))

# This code is contributed by Ryuga
```

## C#

```csharp
// C# implementation of the approach

using System;

public class GFG{

    // Function to return the required sum
    public static int getSum(int []arr, int p)
    {
        return arr.Length;
    }

    // Driver code
    static public void Main (){
        int []arr = { 5, 6, 8 };
        int p = 7;
        Console.WriteLine(getSum(arr, p));
    }

//This Code is contributed by akt_mit    
}
```

## PHP

```php
<?php
// PHP implementation of the approach

// Function to return the required sum
function getSum($arr, $p)
{
    return count($arr);
}

// Driver code
$arr = array( 5, 6, 8 );
$p = 7;
echo (getSum($arr, $p));

// This code is contributed
// by Sach_Code
?>
```

## JavaScript

```javascript
<script>

    // Javascript implementation of the approach

    // Function to return the required sum
    function getSum(arr, p)
    {
        return arr.length;
    }

    let arr = [ 5, 6, 8 ];
    let p = 7;
    document.write(getSum(arr, p));

</script>
```

**Output：**

```