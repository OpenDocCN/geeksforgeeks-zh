# 生成由满足给定条件的字符‘a’和‘b’组成的字符串

> 原文: [https://www.geeksforgeeks.org/generate-a-string-consisting-of-characters-a-and-b-that-satisfy-the-given-conditions/](https://www.geeksforgeeks.org/generate-a-string-consisting-of-characters-a-and-b-that-satisfy-the-given-conditions/)

给定两个整数 `A` 和 `B`，任务是生成并打印一个字符串 `str`，这样：

1.  `str` 必须只包含字符 `'a'` 和 `'b'`。
2.  `str` 长度为 `A + B`，字符 `'a'` 的出现次数等于 `A`，字符 `'b'` 的出现次数等于 `B`。
3.  子串 `"aaa"` 或 `"bbb"` 不得出现在 `str` 中。

**注意**：对于 `A` 和 `B` 的给定值，总是可以生成一个有效的字符串。

**举例：**

> **输入：** `A = 1`，`B = 2`
> **输出：** `abb`
> `"abb"`、`"bab"`、`"bba"` 均为有效字符串。
> **输入：** `A = 4`，`B = 1`
> **输出：** `aabaa`

## 进场

*   如果 `count(a) > count(b)`，则追加 `"aab"`。
*   如果 `count(b) > count(a)`，则追加 `"bba"`。
*   如果 `count(a) = count(b)`，则追加 `"ab"`。

由于我们在每次迭代中最多将 `'a'` 和 `'b'` 的出现次数之差减少 1，因此 `"bba"` 和 `"aab"` 保证不会分别跟在 `"aab"` 和 `"bba"` 之后。

以下是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to generate and print the required string
void generateString(int A, int B)
{
    string rt;
    while (0 < A || 0 < B) {

        // More 'b', append "bba"
        if (A < B) {
            if (0 < B--)
                rt.push_back('b');
            if (0 < B--)
                rt.push_back('b');
            if (0 < A--)
                rt.push_back('a');
        }

        // More 'a', append "aab"
        else if (B < A) {
            if (0 < A--)
                rt.push_back('a');
            if (0 < A--)
                rt.push_back('a');
            if (0 < B--)
                rt.push_back('b');
        }

        // Equal number of 'a' and 'b'
        // append "ab"
        else {
            if (0 < A--)
                rt.push_back('a');
            if (0 < B--)
                rt.push_back('b');
        }
    }
    cout << rt;
}

// Driver code
int main()
{
    int A = 2, B = 6;
    generateString(A, B);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG
{

    // Function to generate and
    // print the required string
    static void generateString(int A, int B)
    {
        String rt = "";
        while (0 < A || 0 < B)
        {

            // More 'b', append "bba"
            if (A < B)
            {
                if (0 < B--)
                {
                    rt += ('b');
                }
                if (0 < B--)
                {
                    rt += ('b');
                }
                if (0 < A--)
                {
                    rt += ('a');
                }
            }

            // More 'a', append "aab"
            else if (B < A)
            {
                if (0 < A--)
                {
                    rt += ('a');
                }
                if (0 < A--)
                {
                    rt += ('a');
                }
                if (0 < B--)
                {
                    rt += ('b');
                }
            }

            // Equal number of 'a' and 'b'
            // append "ab"
            else
            {
                if (0 < A--)
                {
                    rt += ('a');
                }
                if (0 < B--)
                {
                    rt += ('b');
                }
            }
        }
        System.out.println(rt);
    }

    // Driver code
    public static void main(String[] args)
    {
        int A = 2, B = 6;
        generateString(A, B);
    }
}

// This code is contributed
// by PrinciRaj1992
```

## Python 3

```python
# Python 3 implementation of the approach

# Function to generate and print
# the required string
def generateString(A, B):

    rt = ""
    while (0 < A or 0 < B) :

        # More 'b', append "bba"
        if (A < B) :
            if (0 < B):
                rt = rt +'b'
                B -= 1
            if (0 < B):
                rt += 'b'
                B -= 1
            if (0 < A):
                rt += 'a'
                A -= 1

        # More 'a', append "aab"
        elif (B < A):
            if (0 < A):
                rt += 'a'
                A -= 1
            if (0 < A):
                rt += 'a'
                A -= 1
            if (0 < B):
                rt += 'b'
                B -= 1

        # Equal number of 'a' and 'b'
        # append "ab"
        else :
            if (0 < A):
                rt += 'a'
                A -= 1
            if (0 < B):
                rt += 'b'
                B -= 1
    print(rt)

# Driver code
if __name__ == "__main__":

    A = 2
    B = 6
    generateString(A, B)

# This code is contributed by ita_c
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

    // Function to generate and
    // print the required string
    static void generateString(int A, int B)
    {
        string rt = "";
        while (0 < A || 0 < B)
        {

            // More 'b', append "bba"
            if (A < B)
            {
                if (0 < B--)
                {
                    rt += ('b');
                }
                if (0 < B--)
                {
                    rt += ('b');
                }
                if (0 < A--)
                {
                    rt += ('a');
                }
            }

            // More 'a', append "aab"
            else if (B < A)
            {
                if (0 < A--)
                {
                    rt += ('a');
                }
                if (0 < A--)
                {
                    rt += ('a');
                }
                if (0 < B--)
                {
                    rt += ('b');
                }
            }

            // Equal number of 'a' and 'b'
            // append "ab"
            else
            {
                if (0 < A--)
                {
                    rt += ('a');
                }
                if (0 < B--)
                {
                    rt += ('b');
                }
            }
        }
        Console.WriteLine(rt);
    }

    // Driver code
    public static void Main()
    {
        int A = 2, B = 6;
        generateString(A, B);
    }
}

// This code is contributed by Ryuga
```

## PHP

```php
<?php
// PHP implementation of the approach

// Function to generate and
// print the required string
function generateString($A, $B)
{
    $rt = "";
    while (0 < $A || 0 < $B)
    {

        // More 'b', append "bba"
        if ($A < $B)
        {
            if (0 < $B--)
            {
                $rt .= ('b');
            }
            if (0 < $B--)
            {
                $rt .= ('b');
            }
            if (0 < $A--)
            {
                $rt .= ('a');
            }
        }

        // More 'a', append "aab"
        else if ($B < $A)
        {
            if (0 < $A--)
            {
                $rt .= ('a');
            }
            if (0 < $A--)
            {
                $rt .= ('a');
            }
            if (0 < $B--)
            {
                $rt .= ('b');
            }
        }

        // Equal number of 'a' and 'b'
        // append "ab"
        else
        {
            if (0 < $A--)
            {
                $rt .= ('a');
            }
            if (0 < $B--)
            {
                $rt .= ('b');
            }
        }
    }
    echo($rt);
}

// Driver code
$A = 2; $B = 6;
generateString($A, $B);

// This code is contributed
// by Code Mech
?>
```

## java 描述语言

```javascript
<script>
// Javascript implementation of the approach

// Function to generate and
// print the required string
function generateString(A, B) {
    let rt = "";
    while (0 < A || 0 < B) {
        // More 'b', append "bba"
        if (A < B) {
            if (0 < B--) {
                rt += ('b');
            }
            if (0 < B--) {
                rt += ('b');
            }
            if (0 < A--) {
                rt += ('a');
            }
        }
        // More 'a', append "aab"
        else if (B < A) {
            if (0 < A--) {
                rt += ('a');
            }
            if (0 < A--) {
                rt += ('a');
            }
            if (0 < B--) {
                rt += ('b');
            }
        }
        // Equal number of 'a' and 'b'
        // append "ab"
        else {
            if (0 < A--) {
                rt += ('a');
            }
            if (0 < B--) {
                rt += ('b');
            }
        }
    }
    document.write(rt);
}

// Driver code
let A = 2, B = 6;
generateString(A, B);

// This code is contributed by avanitrachhadiya2155
</script>
```

**Output:**

```
bbabbabb
```