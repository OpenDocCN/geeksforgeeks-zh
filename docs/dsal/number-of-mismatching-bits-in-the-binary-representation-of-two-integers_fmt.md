# 两个整数的二进制表示中不匹配的位数

> 原文：[https://www.geeksforgeeks.org/number-of-mismatching-bits-in-the-binary-representation-of-two-integers/](https://www.geeksforgeeks.org/number-of-mismatching-bits-in-the-binary-representation-of-two-integers/)

给定两个整数（小于 `2^31`）`A` 和 `B`，任务是找出二进制表示中不同的位数。

**例：**

```
Input :  A = 12, B = 15
Output : Number of different bits : 2
Explanation: The binary representation of 
12 is 1100 and 15 is 1111.
So, the number of different bits are 2.

Input : A = 3, B = 16
Output : Number of different bits : 3
```

**方法：**

*   从 `0` 循环到 `31`，将 `A` 和 `B` 的位向右移动 `i` 位，然后检查第 `0` 位是否不同。
*   如果位不同，则增加计数。
*   由于数字小于 `2^31`，我们只需要循环 `32` 次，即从 `0` 到 `31`。
*   如果我们逐位与 `1` 进行 `AND` 操作，就可以得到第一位。
*   在循环结束时显示计数。

下面是上述方法的实现：

## C++

```c++
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// compute number of different bits
void solve(int A, int B)
{
    int count = 0;

    // since, the numbers are less than 2^31
    // run the loop from '0' to '31' only
    for (int i = 0; i < 32; i++) {

        // right shift both the numbers by 'i' and
        // check if the bit at the 0th position is different
        if (((A >> i) & 1) != ((B >> i) & 1)) {
            count++;
        }
    }

    cout << "Number of different bits : " << count << endl;
}

// Driver code
int main()
{
    int A = 12, B = 15;

    // find number of different bits
    solve(A, B);

    return 0;
}
```

## Java

```java
// Java implementation of the approach

import java.io.*;

class GFG {

// compute number of different bits
static void solve(int A, int B)
{
    int count = 0;

    // since, the numbers are less than 2^31
    // run the loop from '0' to '31' only
    for (int i = 0; i < 32; i++) {

        // right shift both the numbers by 'i' and
        // check if the bit at the 0th position is different
        if (((A >> i) & 1) != ((B >> i) & 1)) {
            count++;
        }
    }

    System.out.println("Number of different bits : " + count);
}

// Driver code

    public static void main (String[] args) {
        int A = 12, B = 15;

    // find number of different bits
    solve(A, B);

    }
}
// this code is contributed by anuj_67..
```

## Python 3

```python
# Python3 implementation of the approach

# compute number of different bits
def solve( A,  B):

    count = 0

    # since, the numbers are less than 2^31
    # run the loop from '0' to '31' only
    for i in range(0,32):

        # right shift both the numbers by 'i' and
        # check if the bit at the 0th position is different
        if ((( A >>  i) & 1) != (( B >>  i) & 1)):
             count=count+1

    print("Number of different bits :",count)

# Driver code
A = 12
B = 15

# find number of different bits
solve( A,  B)

# This code is contributed by ihritik
```

## C#

```csharp
// C# implementation of the approach

using System;
class GFG
{
    // compute number of different bits
    static void solve(int A, int B)
    {
        int count = 0;

        // since, the numbers are less than 2^31
        // run the loop from '0' to '31' only
        for (int i = 0; i < 32; i++) {

            // right shift both the numbers by 'i' and
            // check if the bit at the 0th position is different
            if (((A >> i) & 1) != ((B >> i) & 1)) {
                count++;
            }
        }

        Console.WriteLine("Number of different bits : " + count);
    }

    // Driver code
    public static void  Main()
    {
        int A = 12, B = 15;

        // find number of different bits
        solve(A, B);

    }

}

// This code is contributed by ihritik
```

## PHP

```php
<?php
// PHP implementation of the approach

// compute number of different bits
function solve($A, $B)
{
    $count = 0;

    // since, the numbers are less than 2^31
    // run the loop from '0' to '31' only
    for ($i = 0; $i < 32; $i++) {

        // right shift both the numbers by 'i' and
        // check if the bit at the 0th position is different
        if ((($A >> $i) & 1) != (($B >> $i) & 1)) {
            $count++;
        }
    }

    echo "Number of different bits : $count";
}

// Driver code
$A = 12;
$B = 15;

// find number of different bits
solve($A, $B);

// This code is contributed by ihritik
?>
```

## JavaScript

```javascript
<script>

// Javascript implementation of the approach

// Compute number of different bits
function solve(A, B)
{
    var count = 0;

    // Since, the numbers are less than 2^31
    // run the loop from '0' to '31' only
    for(i = 0; i < 32; i++)
    {

        // Right shift both the numbers by 'i'
        // and check if the bit at the 0th
        // position is different
        if (((A >> i) & 1) != ((B >> i) & 1))
        {
            count++;
        }
    }
    document.write("Number of different bits : " +
                   count);
}

// Driver code   
var A = 12, B = 15;

// Find number of different bits
solve(A, B);

// This code is contributed by Rajput-Ji

</script>
```

**Output**

```
Number of different bits : 2
```

**一种不同的方法使用 XOR（^）：**

*   求两个数 `A` 和 `B` 的差或（），例如 `A` 和 `B`。
*   并让 `A` 和 `B` 的 `XOR` 结果成为 `C`。
*   计算 `C` 的二进制表示中置位（`1`）的数量。
*   返回计数。

例：

*   设 `A = 10`（`01010`）和 `B = 20`（`10100`）
*   对 `A` 和 `B` 进行 `XOR` 后得到 `XOR = 11110`（如有需要可查看 `XOR` 表）。
*   计算 `XOR` 操作中 `1` 的数量，即可得到 `A` 和 `B` 之间的位差计数（使用 Brian Kernighan 算法）。

下面是上述方法的实现：

## C++

```c++
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// compute number of different bits
int solve(int A, int B)
{
    int XOR = A ^ B;
    // Check for 1's in the binary form using
    // Brian Kerninghan's Algorithm
    int count = 0;
    while (XOR) {
        XOR = XOR & (XOR - 1);
        count++;
    }
    return count;
}

// Driver code
int main()
{
    int A = 12, B = 15;
    // 12 = 1100 & 15 = 1111
    int result = solve(A, B);
    cout << "Number of different bits : " << result;

    return 0;
}
// the code is by Samarpan Chakraborty
```

## Java

```java
/*package whatever //do not write package name here */
// Java implementation of the approach
import java.io.*;

class GFG {

    // compute number of different bits
    static int solve(int A, int B)
    {
        int XOR = A ^ B;
        // Check for 1's in the binary form using
        // Brian Kerninghan's Algorithm
        int count = 0;
        while (XOR > 0) {
            XOR = XOR & (XOR - 1);
            count++;
        }
        // return the count of different bits
        return count;
    }

    public static void main(String[] args)
    {
        int A = 12, B = 15;

        // find number of different bits
        int result = solve(A, B);
        System.out.println("Number of different bits : "
                           + result);
    }
}
// the code is by Samarpan Chakraborty
```

## Python 3

```python
# code
def solve(A, B):
    XOR = A ^ B
    count = 0
    # Check for 1's in the binary form using
    # Brian Kernighan's Algorithm
    while (XOR):
        XOR = XOR & (XOR - 1)
        count += 1
    return count

result = solve(3, 16)
# 3 = 00011 & 16 = 10000
print("Number of different bits : ", result)

# the code is by Samarpan Chakraborty
```

## C\#

```csharp
// C# program for the above approach
using System;
class GFG {

   // compute number of different bits
    static int solve(int A, int B)
    {
        int XOR = A ^ B;

        // Check for 1's in the binary form using
        // Brian Kerninghan's Algorithm
        int count = 0;
        while (XOR > 0) {
            XOR = XOR & (XOR - 1);
            count++;
        }
        // return the count of different bits
        return count;
    }

// Driver code
public static void Main()
{
    int A = 12, B = 15;

        // find number of different bits
        int result = solve(A, B);
        Console.WriteLine("Number of different bits : "
                           + result);
}
}

// This code is contributed by target_2.
```

## Javascript

```javascript
<script>

/*package whatever //do not write package name here */
// JavaScript implementation of the approach
// compute number of different bits
function solve(A, B)
{
        var XOR = A ^ B;

        // Check for 1's in the binary form using
        // Brian Kerninghan's Algorithm
        var count = 0;
        while (XOR > 0) {
            XOR = XOR & (XOR - 1);
            count++;
        }

        // return the count of different bits
        return count;
    }

        var A = 12, B = 15;

        // find number of different bits
        var result = solve(A, B);
        document.write("Number of different bits : "
                           + result);

// This code is contributed by shivanisinghss2110
</script>
```

### 输出

[`布莱恩·克尼根的算法`](https://www.geeksforgeeks.org/count-set-bits-in-an-integer/)