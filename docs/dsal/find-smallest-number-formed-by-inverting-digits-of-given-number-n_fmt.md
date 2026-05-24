# 求给定数 N 的数字反相形成的最小数

> 原文：[https://www.geeksforgeeks.org/find-smallest-number-formed-by-inverting-digits-of-given-number-n/](https://www.geeksforgeeks.org/find-smallest-number-formed-by-inverting-digits-of-given-number-n/)

给定一个整数 `N`，任务是通过反转 `N` 的一些数字来形成一个最小可能正数（> 0）。

> 数字 `T` 的反相定义为从 9 减去 `T`，即 `9–T`。

**注：** 最终数字不应该从零开始。

**示例：**

> **输入：** `N = 4545`
> **输出：** `4444`
> **解释：**
> 最小可能数为 `4444`，通过将两个 `5` 反相（`9–5 = 4`）得到。
>
> **输入：** `N = 9000`
> **输出：** `9000`
> **解释：**
> 最小可能数为 `9000`，因为该数必须为 > 0，因此不能从其自身减去 `9`。

## 方法

想法是迭代给定数字中的所有数字，检查 `9–current_digit` 是否小于 `current_digit`，然后用 `9–current_digit` 替换该数字，否则不要更改数字。如果数字的第一个数字是 `9`，那么不要改变数字，我们不能在形成的新数字中有尾随零。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <iostream>
using namespace std;

// Function to invert the digits of
// integer N to form minimum
// possible number
void number(int num)
{
    // Initialize the array
    int a[20], r, i = 0, j;

    // Iterate till the number N exists
    while (num > 0) {

        // Last digit of the number N
        r = num % 10;

        // Checking if the digit is
        // smaller than 9-digit
        if (9 - r > r)

            // Store the smaller
            // digit in the array
            a[i] = r;

        else
            a[i] = 9 - r;

        i++;

        // Reduce the number each time
        num = num / 10;
    }

    // Check if the digit starts
    // with 0 or not
    if (a[i - 1] == 0) {
        cout << 9;
        i--;
    }

    // Print the answer
    for (j = i - 1; j >= 0; j--)
        cout << a[j];
}

// Driver Code
int main()
{
    // Given Number
    long long int num = 4545;

    // Function Call
    number(num);

    return 0;
}
```

### Java

```java
// Java program for the above approach
class GFG{

// Function to invert the digits of
// integer N to form minimum
// possible number
static void number(int num)
{
    // Initialize the array
    int a[] = new int[20];
    int r, i = 0, j;

    // Iterate till the number N exists
    while (num > 0)
    {

        // Last digit of the number N
        r = num % 10;

        // Checking if the digit is
        // smaller than 9-digit
        if (9 - r > r)

            // Store the smaller
            // digit in the array
            a[i] = r;

        else
            a[i] = 9 - r;

        i++;

        // Reduce the number each time
        num = num / 10;
    }

    // Check if the digit starts
    // with 0 or not
    if (a[i - 1] == 0)
    {
        System.out.print("9");
        i--;
    }

    // Print the answer
    for (j = i - 1; j >= 0; j--)
        System.out.print(a[j]);
}

// Driver Code
public static void main(String []args)
{
    // Given Number
     int num = 4545;

    // Function Call
    number(num);
}
}

// This code is contributed by rock_cool
```

### Python 3

```python
# Python3 program for the above approach

# Function to invert the digits of
# integer N to form minimum
# possible number
def number(num):

    # Initialize the array
    a = [0] * 20
    r, i, j = 0, 0, 0

    # Iterate till the number N exists
    while (num > 0):

        # Last digit of the number N
        r = num % 10

        # Checking if the digit is
        # smaller than 9-digit
        if (9 - r > r):

            # Store the smaller
            # digit in the array
            a[i] = r

        else:
            a[i] = 9 - r

        i += 1

        # Reduce the number each time
        num = num // 10

    # Check if the digit starts
    # with 0 or not
    if (a[i - 1] == 0):
        print(9, end = "")
        i -= 1

    # Print the answer
    for j in range(i - 1, -1, -1):
        print(a[j], end = "")

# Driver Code
if __name__ == '__main__':

    # Given Number
    num = 4545

    # Function Call
    number(num)

# This code is contributed by Mohit Kumar
```

### C#

```csharp
// C# program for the above approach
using System;
class GFG{

// Function to invert the digits of
// integer N to form minimum
// possible number
static void number(int num)
{
    // Initialize the array
    int[] a = new int[20];
    int r, i = 0, j;

    // Iterate till the number N exists
    while (num > 0)
    {

        // Last digit of the number N
        r = num % 10;

        // Checking if the digit is
        // smaller than 9-digit
        if (9 - r > r)

            // Store the smaller
            // digit in the array
            a[i] = r;

        else
            a[i] = 9 - r;

        i++;

        // Reduce the number each time
        num = num / 10;
    }

    // Check if the digit starts
    // with 0 or not
    if (a[i - 1] == 0)
    {
        Console.Write("9");
        i--;
    }

    // Print the answer
    for (j = i - 1; j >= 0; j--)
        Console.Write(a[j]);
}

// Driver Code
public static void Main(string []args)
{
    // Given Number
     int num = 4545;

    // Function Call
    number(num);
}
}

// This code is contributed by Ritik Bansal
```

### JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to invert the digits of
// integer N to form minimum
// possible number
function number(num)
{

    // Initialize the array
    let a = new Array(20);
    let r, j;
    let i = 0;

    // Iterate till the number N exists
    while (num > 0)
    {

        // Last digit of the number N
        r = num % 10;

        // Checking if the digit is
        // smaller than 9-digit
        if (9 - r > r)

            // Store the smaller
            // digit in the array
            a[i] = r;

        else
            a[i] = 9 - r;

        i++;

        // Reduce the number each time
        num = parseInt(num / 10, 10);
    }

    // Check if the digit starts
    // with 0 or not
    if (a[i - 1] == 0)
    {
        document.write(9);
        i--;
    }

    // Print the answer
    for(j = i - 1; j >= 0; j--)
        document.write(a[j]);
}

// Driver code

// Given Number
let num = 4545;

// Function Call
number(num);

// This code is contributed by divyesh072019

</script>
```

**输出：**

```
4444
```

**时间复杂度：** `O(log<sub>10</sub>N)`
**辅助空间：** `O(log<sub>10</sub>N)`