# 求第 k 个最小奇数长度回文数

> 原文：[https://www.geeksforgeeks.org/find-the-kth-smallest-odd-length-palindrome-number/](https://www.geeksforgeeks.org/find-the-kth-smallest-odd-length-palindrome-number/)

给定一个正整数 `K`，任务是找到第 `K` 个最小的[奇数长度回文数](https://www.geeksforgeeks.org/python-program-check-string-palindrome-not/)。

**示例：**

> **输入：** `K = 5`
> **输出：** `5`
> **解释：**
> 奇数长度的回文数为 {1, 2, 3, 4, 5, 6, 7, ...}。第 5 个最小回文数是 5。
>
> **输入：** `K = 10`
> **输出：** `101`

**方法：** 给定的问题可以基于以下观察来解决：

*   长度为 1 的第一个[回文数字](https://www.geeksforgeeks.org/python-program-check-string-palindrome-not/)是 1、2、3、4、5、6、7、8 和 9。
*   长度为 3 的第一个回文数是 101，这是第十个最小的奇数长度回文数。同样，第 11 次、第 12 次、第 13 次、...、第 99 次最小回文数分别为 111、121、131 ...、999。
*   因此，除最后一位数字外，第 `K` 个最小奇数长度回文数可以通过连接 `K` 和 `K` 的倒数构成。

从上面的观察来看，第 `K` 个最小的奇数长度回文数是通过追加除了最后一个在 `K` 末尾的数字之外的 `K` 的所有数字的倒数给出的。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the Kth smallest
// odd length palindrome
int oddLengthPalindrome(int k)
{

    // Store the original number K
    int palin = k;

    // Removing the last digit of K
    k = k / 10;

    // Generate the palindrome by
    // appending the reverse of K
    // except last digit to itself
    while (k > 0)
    {

        // Find the remainder
        int rev = k % 10;

        // Add the digit to palin
        palin = (palin * 10) + rev;

        // Divide K by 10
        k = k / 10;
    }

    // Return the resultant palindromic
    // number formed
    return palin;
}

// Driver Code
int main()
{
    int k = 504;

    cout << oddLengthPalindrome(k);
}

// This code is contributed by rishavmahato348
```

## Java

```java
// Java program for the above approach
import java.util.*;
import java.lang.*;

class GFG{

// Function to find the Kth smallest
// odd length palindrome
static int oddLengthPalindrome(int k)
{

    // Store the original number K
    int palin = k;

    // Removing the last digit of K
    k = k / 10;

    // Generate the palindrome by
    // appending the reverse of K
    // except last digit to itself
    while (k > 0)
    { 

        // Find the remainder
        int rev = k % 10;

        // Add the digit to palin
        palin = (palin * 10) + rev;

        // Divide K by 10
        k = k / 10;
    }

    // Return the resultant palindromic
    // number formed
    return palin;
}

// Driver Code
public static void main(String[] args)
{
    int k = 504;

    System.out.println(oddLengthPalindrome(k));
}
}

// This code is contributed by Sudhanshu Bhagat & Govind Choudhary
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the Kth smallest
# odd length palindrome number
def oddLengthPalindrome(K):

    # Store the original number K
    palin = K

    # Removing the last digit of K
    K = K // 10

    # Generate the palindrome by
    # appending the reverse of K
    # except last digit to itself
    while (K > 0):

        # Find the remainder
        rev = K % 10

        # Add the digit to palin
        palin = palin * 10 + rev

        # Divide K by 10
        K = K // 10

    # Return the resultant palindromic
    # number formed
    return palin

# Driver Code
if __name__ == '__main__':

    K = 504
    print(oddLengthPalindrome(K))

#Contributed by Govind Choudhary & Pallav Pushparaj
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find the Kth smallest
// palindrome of odd length
static int oddLengthPalindrome(int k)
{

    // Store the original number K
    int palin = k;

    // Removing the last digit of K
    k = k / 10;

    // Generate the palindrome by
    // appending the reverse of K
    // except last digit to itself
    while (k > 0)
    {

        // Find the remainder
        int rev = k % 10;

        // Add the digit to palin
        palin = (palin * 10) + rev;

        // Divide K by 10
        k = k / 10;
    }

    // Return the resultant palindromic
    // number formed
    return palin;
}

// Driver Code
static void Main(string[] args)
{
    int k = 504;

    Console.WriteLine(oddLengthPalindrome(k));
}
}

// This code is contributed by Sudhanshu Bhagat & Govind Choudhary
```

## JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Function to find the Kth smallest
// odd length palindrome
function oddLengthPalindrome(k)
{

    // Store the original number K
    let palin = k;

    // Removing the last digit of K
    k = Math.floor(k / 10);

    // Generate the palindrome by
    // appending the reverse of K
    // except last digit to itself
    while (k > 0)
    { 

        // Find the remainder
        let rev = k % 10;

        // Add the digit to palin
        palin = (palin * 10) + rev;

        // Divide K by 10
        k = Math.floor(k / 10);
    }

    // Return the resultant palindromic
    // number formed
    return palin;
}

// Driver Code

    let k = 504;

    document.write(oddLengthPalindrome(k));

// This code is contributed by sanjoy_62.
</script>
```

**输出：**

```
50405
```

**时间复杂度：** O(log<sub>10</sub>K)
**辅助空间：** O(1)