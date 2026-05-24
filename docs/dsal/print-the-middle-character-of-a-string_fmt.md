# 打印字符串的中间字符

> 原文：[https://www.geeksforgeeks.org/print-the-middle-character-of-a-string/](https://www.geeksforgeeks.org/print-the-middle-character-of-a-string/)

给定字符串 `str`，任务是打印字符串的中间字符。如果字符串的长度是偶数，那么会有两个中间字符，我们需要打印第二个中间字符。

**示例：**

> **输入：** `str = "Java"`
> **输出：** `v`
> **解释：**
> 给定字符串的长度是偶数。
> 因此，会有两个中间字符‘a’和‘v’，我们打印第二个中间字符。
>
> **输入：** `str = "GeeksForGeeks"`
> **输出：** `o`
> **解释：**
> 给定字符串的长度是奇数。
> 因此，只有一个中间字符，我们打印该中间字符。

## 算法描述

1.  获取要找到中间字符的字符串。
2.  计算给定字符串的长度。
3.  查找字符串的中间索引。
4.  现在，使用 Java 中的函数 `charAt()` 在索引 `middle` 处打印字符串的中间字符。

下面是上述方法的实现：

## 代码实现

### C++

```cpp
// C++ program to implement
// the above approach
#include<bits/stdc++.h>
using namespace std;

// Function that prints the middle
// character of a string
void printMiddleCharacter(string str)
{
    // Finding string length
    int len = str.size();

    // Finding middle index of string
    int middle = len / 2;

    // Print the middle character
    // of the string
    cout << str[middle];
}

// Driver Code
int main()
{
    // Given string str
    string str = "GeeksForGeeks";

    // Function Call
    printMiddleCharacter(str);
    return 0;
}

// This code is contributed by Sapnasingh
```

### Java

```java
// Java program for the above approach
class GFG {

    // Function that prints the middle
    // character of a string
    public static void
    printMiddleCharacter(String str)
    {
        // Finding string length
        int len = str.length();

        // Finding middle index of string
        int middle = len / 2;

        // Print the middle character
        // of the string
        System.out.println(str.charAt(middle));
    }

    // Driver Code
    public static void
    main(String args[])
    {
        // Given string str
        String str = "GeeksForGeeks";

        // Function Call
        printMiddleCharacter(str);
    }
}
```

### Python 3

```python
# Python3 program for the above approach

# Function that prints the middle
# character of a string
def printMiddleCharacter(str):

    # Finding string length
    length = len(str);

    # Finding middle index of string
    middle = length // 2;

    # Print the middle character
    # of the string
    print(str[middle]);

# Driver Code

# Given string str
str = "GeeksForGeeks";

# Function Call
printMiddleCharacter(str);

# This code is contributed by sapnasingh4991
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function that prints the middle
// character of a string
public static void printMiddlechar(String str)
{

    // Finding string length
    int len = str.Length;

    // Finding middle index of string
    int middle = len / 2;

    // Print the middle character
    // of the string
    Console.WriteLine(str[middle]);
}

// Driver Code
public static void Main(String []args)
{

    // Given string str
    String str = "GeeksForGeeks";

    // Function call
    printMiddlechar(str);
}
}

// This code is contributed by amal kumar choubey
```

### JavaScript

```javascript
<script>
    // Javascript program for the above approach

    // Function that prints the middle
    // character of a string
    function printMiddleCharacter(str)
    {
        // Finding string length
        let len = str.length;

        // Finding middle index of string
        let middle = parseInt(len / 2, 10);

        // Print the middle character
        // of the string
        document.write(str[middle]);
    }

    // Given string str
    let str = "GeeksForGeeks";

    // Function Call
    printMiddleCharacter(str);

// This code is contributed by divyeshrabadiya07.
</script>
```

**输出：**

```
o
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`