# 表示基数-2中的数字N

> 原文：[https://www.geeksforgeeks.org/represent-a-number-n-in-base-2/](https://www.geeksforgeeks.org/represent-a-number-n-in-base-2/)

给定一个整数`N`，任务是以[字符串](https://www.geeksforgeeks.org/category/data-structures/c-strings/)的形式找到数字`N`的`base -2`表示，使得`S0*(-2)^0 + S1*(-2)^1 + … + Sk*(-2)^k = N`。[字符串](https://www.geeksforgeeks.org/category/data-structures/c-strings/)应该只由`0`和`1`组成，除非[字符串](https://www.geeksforgeeks.org/category/data-structures/c-strings/)等于`"0"`，其首字符应该是`1`。

**示例：**

> **输入：** `N = -9`
> **输出：** `1011`
> **解释：** `1011`是`-9`的`-2`进制表示。
> `(-2)^0 + (-2)^1 + (-2)^3 = 1 + (-2) + (-8) = -9`
>
> **输入：** `N = -7`
> **输出：** `1001`

**方法：** 按照以下步骤解决问题：

*   初始化一个空的[字符串](https://www.geeksforgeeks.org/category/data-structures/c-strings/)`S`。
*   从`N`开始迭代，直到`N`大于`0`。
    *   如果`N`为偶数，则在`S`前追加`"0"`，用`-2`除`N`。
    *   否则，在`S`前追加`"1"`，用`1`减去`N`，再用`-2`除`N`。
*   如果[字符串](https://www.geeksforgeeks.org/category/data-structures/c-strings/)`S`为空，则返回`"0"`。
*   最后，返回[字符串](https://www.geeksforgeeks.org/category/data-structures/c-strings/)`S`。

下面是上述方法的实现：

## C++

```cpp
// C++ Program for above approach
#include <bits/stdc++.h>
using namespace std;

// Function to convert N to
// equivalent representation in base -2
string BaseConversion(int N)
{

    // Stores the required answer
    string s = "";

    // Iterate until N is
    // not equal to zero
    while (N != 0) {

        // If N is Even
        if (N % 2 == 0) {

            // Add char '0' in
            // front of string
            s = "0" + s;
        }
        else {

            // Add char '1' in
            // front of string
            s = "1" + s;

            // Decrement N by 1
            N--;
        }

        // Divide N by -2
        N /= -2;
    }

    // If string is empty,
    // that means N is zero
    if (s == "") {

        // Put '0' in string s
        s = "0";
    }
    return s;
}

// Driver Code
int main()
{

    // Given Input
    int N = -9;

    // Function Call
    cout << BaseConversion(N);
    return 0;
}
```

## Java

```java
// Java Program for above approach
class GFG {
    // Function to convert N to
    // equivalent representation in base -2
    public static String BaseConversion(int N) {

        // Stores the required answer
        String s = "";

        // Iterate until N is
        // not equal to zero
        while (N != 0) {

            // If N is Even
            if (N % 2 == 0) {

                // Add char '0' in
                // front of string
                s = "0" + s;
            } else {

                // Add char '1' in
                // front of string
                s = "1" + s;

                // Decrement N by 1
                N--;
            }

            // Divide N by -2
            N /= -2;
        }

        // If string is empty,
        // that means N is zero
        if (s == "") {

            // Put '0' in string s
            s = "0";
        }
        return s;
    }

    // Driver Code
    public static void main(String args[]) {

        // Given Input
        int N = -9;

        // Function Call
        System.out.println(BaseConversion(N));
    }

}

// This code is contributed by _saurabh_jaiswal.
```

## Python 3

```python
# Python Program for the above approach

# Function to convert N to
# equivalent representation in base -2
def BaseConversion(N):

    # Stores the required answer
    s = ""

    # Iterate until N is
    # not equal to zero
    while (N != 0):

        # If N is Even
        if (N % 2 == 0):

            # Add char '0' in
            # front of string
            s = "0" + s

        else:

            # Add char '1' in
            # front of string
            s = "1" + s

            # Decrement N by 1
            N -= 1

        # Divide N by -2
        N //= -2

    # If string is empty,
    # that means N is zero
    if (s == ""):

        # Put '0' in string s
        s = "0"

    return s

# Driver Code

# Given Input
N = -9

# Function Call
print(BaseConversion(N))

# This code is contributed by _saurabh_jaiswal
```

## C#

```csharp
// C# Program for above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to convert N to
// equivalent representation in base -2
static string BaseConversion(int N)
{

    // Stores the required answer
    string s = "";

    // Iterate until N is
    // not equal to zero
    while (N != 0) {

        // If N is Even
        if (N % 2 == 0) {

            // Add char '0' in
            // front of string
            s = "0" + s;
        }
        else {

            // Add char '1' in
            // front of string
            s = "1" + s;

            // Decrement N by 1
            N--;
        }

        // Divide N by -2
        N /= -2;
    }

    // If string is empty,
    // that means N is zero
    if (s == "") {

        // Put '0' in string s
        s = "0";
    }
    return s;
}

// Driver Code
public static void Main()
{

    // Given Input
    int N = -9;

    // Function Call
    Console.Write(BaseConversion(N));
}
}

// This code is contributed by bgangwar59.
```

## JavaScript

```javascript
<script>
       // JavaScript Program for the above approach

       // Function to convert N to
       // equivalent representation in base -2
       function BaseConversion(N)
       {

           // Stores the required answer
           let s = "";

           // Iterate until N is
           // not equal to zero
           while (N != 0) {

               // If N is Even
               if (N % 2 == 0) {

                   // Add char '0' in
                   // front of string
                   s = "0" + s;
               }
               else {

                   // Add char '1' in
                   // front of string
                   s = "1" + s;

                   // Decrement N by 1
                   N--;
               }

               // Divide N by -2
               N /= -2;
           }

           // If string is empty,
           // that means N is zero
           if (s == "") {

               // Put '0' in string s
               s = "0";
           }
           return s;
       }

       // Driver Code

       // Given Input
       let N = -9;

       // Function Call
       document.write(BaseConversion(N));

   // This code is contributed by Potta Lokesh
   </script>
```

**输出：**

```
1011
```

**时间复杂度：** `O(N)`
**辅助空间：** `O(1)`