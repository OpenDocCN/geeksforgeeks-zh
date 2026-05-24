# 统计邻居相同的字符

> 原文: [https://www.geeksforgeeks.org/count-characters-with-same-neighbors/](https://www.geeksforgeeks.org/count-characters-with-same-neighbors/)

给定一个字符串，任务是找出相邻字符相同的字符数。
**注意:** 第一个和最后一个字符将始终被计算在内，因为它们只有一个相邻的字符。

**示例:**

> **输入:** `str = "egeeksk"`
> **输出:** 4
> 相邻字符相同的字符为 `e`、`g`、`s`、`k`
> **输入:** `str = " eeeeee "`
> **输出:** 8
> 相邻字符相同的字符为 `e`、`e`、`e`、`e`、`e`、`e`、`e`、`e`、`e`

## 进场

1.  如果字符串的长度小于 3，则返回字符串的长度。
2.  用 2 初始化计数，因为第一个和最后一个总是被计数。
3.  开始遍历字符串。
    *   检查当前字符的前一个和后一个字符是否相同。
    *   如果是，则递增计数。
4.  返回计数。

## 下面是上述做法的执行情况

### C++

```cpp
// C++ implementation of above approach
#include <bits/stdc++.h>
using namespace std;

// Function to count the characters
// with same adjacent characters
int countChar(string str)
{
    int n = str.length();

    // if length is less than 3
    // then return length as there
    // will be only two characters
    if (n <= 2)
        return n;
    int count = 2;

    // Traverse the string
    for (int i = 1; i < n - 1; i++)

        // Increment the count if the previous
        // and next character is same
        if (str[i - 1] == str[i + 1])
            count++;

    // Return count
    return count;
}

// Driver code
int main()
{
    string str = "egeeksk";
    cout << countChar(str);

    return 0;
}
```

### Java

```java
// Java implementation of the above approach

class GFG
{
    // Function to count the characters
    // with same adjacent characters
    static int countChar(String str)
    {
        int n = str.length();

        // if length is less than 3
        // then return length as there
        // will be only two characters
        if (n <= 2)
            return n;
        int count = 2;

        // Traverse the string
        for (int i = 1; i < n - 1; i++)

            // Increment the count if the previous
            // and next character is same
            if (str.charAt(i - 1) == str.charAt(i + 1))
                count++;

        // Return count
        return count;
    }

    // Driver code
    public static void main(String []args)
    {
        String str = "egeeksk";
        System.out.println(countChar(str));
    }
}

// This code is contributed by ihritik
```

### Python 3

```python
# Python 3 implementation of above approach

# Function to count the characters
# with same adjacent characters
def countChar(str):
    n = len(str)

    # if length is less than 3
    # then return length as there
    # will be only two characters
    if (n <= 2):
        return n
    count = 2

    # Traverse the string
    for i in range(1, n - 1):

        # Increment the count if the previous
        # and next character is same
        if (str[i - 1] == str[i + 1]):
            count += 1

    # Return count
    return count

# Driver code
if __name__ == '__main__':
    str = "egeeksk"
    print(countChar(str))

# This code is contributed by
# Surendra_Gangwar
```

### C#

```csharp
// C# implementation of above approach
using System;

class GFG
{
    // Function to count the characters
    // with same adjacent characters
    static int countChar(String str)
    {
        int n = str.Length;

        // if length is less than 3
        // then return length as there
        // will be only two characters
        if (n <= 2)
            return n;
        int count = 2;

        // Traverse the string
        for (int i = 1; i < n - 1; i++)

            // Increment the count if the previous
            // and next character is same
            if (str[i - 1] == str[i + 1])
                count++;

        // Return count
        return count;
    }

    // Driver code
    public static void Main()
    {
        String str = "egeeksk";
        Console.WriteLine(countChar(str));
    }
}

// This code is contributed by Subhadeep
```

### PHP

```php
<?php
// PHP implementation of above approach

// Function to count the characters
// with same adjacent characters
function countChar($str)
{
    $n = strlen($str);

    // if length is less than 3
    // then return length as there
    // will be only two characters
    if ($n <= 2)
        return $n;
    $count = 2;

    // Traverse the string
    for ($i = 1; $i < $n - 1; $i++)

        // Increment the count if the previous
        // and next character is same
        if ($str[$i - 1] == $str[$i + 1])
            $count++;

    // Return count
    return $count;
}

// Driver code
$str = "egeeksk";
echo countChar($str);

// This code is contributed by Sach
?>
```

### JavaScript

```javascript
<script>
// Javascript implementation of above approach

// Function to count the characters
// with same adjacent characters
function countChar(str)
{
    var n = str.length;

    // if length is less than 3
    // then return length as there
    // will be only two characters
    if (n <= 2)
        return n;
    var count = 2;

    // Traverse the string
    for (var i = 1; i < n - 1; i++)

        // Increment the count if the previous
        // and next character is same
        if (str[i - 1] == str[i + 1])
            count++;

    // Return count
    return count;
}

// Driver code
var str = "egeeksk";
document.write( countChar(str));
</script>
```

**Output:**

```
4
```