# 将 N^2 数分成 n 组相等的和

> 原文: [https://www.geeksforgeeks.org/split-n2-numbers-into-n-groups-of-equal-sum/](https://www.geeksforgeeks.org/split-n2-numbers-into-n-groups-of-equal-sum/)

给定一个偶数 `N`，任务是考虑从 1 到 `N`<sup>2</sup> 的数字，将它们分成 `N` 组相等的和。

**例**:

```
Input: N = 2
Output: {1, 4}, {2, 3}
Two groups of equal sum are 1, 4 and 2,3

Input: N = 4
Output: 
{ 1, 16} { 2, 15} 
{ 3, 14} { 4, 13} 
{ 5, 12} { 6, 11} 
{ 7, 10} { 8, 9}
```

**方法:** 前 `N`<sup>2</sup> 个数字之和的公式: **总和 = (`N`<sup>2</sup> * (`N`<sup>2</sup> + 1)) / 2**。
因此，每组的总和将是 **(`N`<sup>2</sup> + 1) * `N`<sup>2</sup> / 2 / `N`**。
让我们考虑以下类型的对: (1, `N`<sup>2</sup>)、(2, `N`<sup>2</sup> - 1) 等等。
因为 `N`<sup>2</sup> 是偶数，所以每组可以使用正好 `N`/2 个这样的对来制作。

以下是上述方法的实施:

## C++

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print N groups of equal sum
void printGroups(int n)
{
    int x = 1;
    int y = n * n;

    // No. of Groups
    for (int i = 1; i <= n; i++) {

        // n/2 pairs
        for (int j = 1; j <= n / 2; j++) {
            cout << "{ " << x << ", " << y << "} ";
            x++;
            y--;
        }

        cout << endl;
    }
}

// Driver code
int main()
{
    int n = 4;
    printGroups(n);

    return 0;
}
```

## Java

```java
// Java implementation of the above approach

import java.io.*;

class GFG {

// Function to print N groups of equal sum
static void printGroups(int n)
{
    int x = 1;
    int y = n * n;

    // No. of Groups
    for (int i = 1; i <= n; i++) {

        // n/2 pairs
        for (int j = 1; j <= n / 2; j++) {
            System.out.print("{ " + x + ", " + y + "} ");
            x++;
            y--;
        }

        System.out.println();
    }
}

// Driver code

    public static void main (String[] args) {
            int n = 4;
    printGroups(n);
    }
}
// This code is contributed by shs
```

## Python 3

```python
# Python implementation of the above approach

# Function to print N groups of equal sum
def printGroups(n) :

    x = 1
    y = n * n

    # No. of Groups
    for i in range(1, n + 1) :

        # n/2 pairs
        for j in range(1, n // 2 + 1) :

            print("{",x,",",y,"}",end = " ")

            x += 1
            y -= 1

        print()

# Driver code
if __name__ == "__main__" :

    n = 4

    # Function call
    printGroups(n)

# This code is contributed by Ryuga
```

## C#

```csharp
// C# implementation of the
// above approach
using System;

class GFG
{

// Function to print N groups
// of equal sum
static void printGroups(int n)
{
    int x = 1;
    int y = n * n;

    // No. of Groups
    for (int i = 1; i <= n; i++)
    {

        // n/2 pairs
        for (int j = 1; j <= n / 2; j++)
        {
            Console.Write("{ " + x + ", " + y + "} ");
            x++;
            y--;
        }

        Console.WriteLine();
    }
}

// Driver code
public static void Main ()
{
    int n = 4;
    printGroups(n);
}
}

// This code is contributed by shs
```

## PHP

```php
<?php
// PHP implementation of the
// above approach

// Function to print N groups
// of equal sum
function printGroups($n)
{
    $x = 1;
    $y = $n * $n;

    // No. of Groups
    for ($i = 1; $i <= $n; $i++)
    {

        // n/2 pairs
        for ($j = 1; $j <= $n / 2; $j++)
        {
            echo "{ " , $x , ", " , $y , " } ";
            $x++;
            $y--;
        }

        echo "\n";
    }
}

// Driver code
$n = 4;
printGroups($n);

// This code is contributed by shs
?>
```

## JavaScript

```javascript
<script>

// Javascript implementation of the above approach

// Function to print N groups of equal sum
function prletGroups(n)
{
    let x = 1;
    let y = n * n;

    // No. of Groups
    for (let i = 1; i <= n; i++) {

        // n/2 pairs
        for (let j = 1; j <= n / 2; j++) {
            document.write("{ " + x + ", " + y + "} ");
            x++;
            y--;
        }

        document.write("<br/>");
    }
}

// driver program

    let n = 4;
    prletGroups(n);

</script>
```

**Output:**

```
{ 1, 16} { 2, 15} 
{ 3, 14} { 4, 13} 
{ 5, 12} { 6, 11} 
{ 7, 10} { 8, 9}
```