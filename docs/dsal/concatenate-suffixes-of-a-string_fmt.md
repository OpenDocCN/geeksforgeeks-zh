# 连接字符串的后缀

> 原文: [https://www.geeksforgeeks.org/concatenate-suffixes-of-a-string/](https://www.geeksforgeeks.org/concatenate-suffixes-of-a-string/)

给定字符串 `str` 的任务是如下展开字符串: 如果字符串为 `abcd` ，则得到的字符串将是级联形式的 `d` 、 `cd` 、 `bcd` 和 `abcd` ，即 `dcdbcdabcd` 。我们基本上需要连接所有的后缀。

**示例:**

> **输入:** `str = "geeks"`
> **输出:** `sksekseeksgeeks`
>
> **输入:** `str = "abcd"`
> **输出:** `dcdbcdabcd`

## 简单方法:

*   以相反的顺序遍历字符串，即从最后一个索引到第一个索引。
*   打印从当前索引位置到字符串末尾的子字符串。

下面是上述方法的实现:

### C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to print the expansion of the string
void printExpansion(string str)
{
    int size = 0;
    for (int i = str.length() - 1; i >= 0; i--) {

        // Take sub-string from i to n-1
        string subStr = str.substr(i, ++size);

        // Print the sub-string
        cout << subStr;
    }
}

// Driver code
int main()
{
    string str = "geeks";
    printExpansion(str);

    return 0;
}
```

### Java

```java
// Java implementation of the approach

public class GFG {

    // Function to print the expansion of the string
    static void printExpansion(String str)
    {
        for (int i = str.length() - 1; i >= 0; i--) {

            // Take sub-string from i to n-1
            String subStr = str.substring(i);

            // Print the sub-string
            System.out.print(subStr);

        }
    }

    // Driver code
    public static void main(String args[])
    {
        String str = "geeks";
        printExpansion(str);

    }
    // This code is contributed by Ryuga
}
```

### Python 3

```python
# Python3 implementation of the approach

# Function to print the expansion of the string
def printExpansion(str):
    for i in range(len(str)-1, -1, -1):

        # Take sub-string from i to n-1
        for j in range(i, len(str)):
            print(str[j], end ="")

# Driver code
str = "geeks"
printExpansion(str)
```

### C#

```csharp
// C# implementation of the approach
using System;
class GFG {

    // Function to print the expansion of the string
    static void printExpansion(String str)
    {
        for (int i = (int)str.Length - 1; i >= 0; i--) {

            // Take sub-string from i to n-1
            String subStr = str.Substring(i);

            // Print the sub-string
            Console.Write(subStr);

        }
    }

    // Driver code
    static public void Main(String []args)
    {
        String str = "geeks";
        printExpansion(str);

    }
}
// This code is contributed by Arnab Kundu
```

### JavaScript

```javascript
<script>

// Javascript implementation of the approach

// Function to print the expansion of the string
function printExpansion(str)
{
    var size = 0;
    for (var i = str.length - 1; i >= 0; i--) {

        // Take sub-string from i to n-1
        var subStr = str.substring(i, i + ++size);

        // Print the sub-string
        document.write( subStr);
    }
}

// Driver code
var str = "geeks";
printExpansion(str);

</script>
```

**输出:**

```
sksekseeksgeeks
```

## 高效方法:

维护后缀字符串(最初为空)。继续从末尾遍历并继续追加当前字符。

### C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to print the expansion of the string
void printExpansion(string str)
{
    string suff = "";
    for (int i = str.length() - 1; i >= 0; i--) {

        // Take sub-string from i to n-1
        suff = suff + str[i];

        // Print the sub-string
        cout << suff;
    }
}

// Driver code
int main()
{
    string str = "geeks";
    printExpansion(str);

    return 0;
}
```

### Java

```java
// Java implementation of the approach
import java.util.*;

class solution
{

// Function to print the expansion of the string
static void printExpansion(String str)
{
    String suff = "";
    for (int i = str.length() - 1; i >= 0; i--) {

        // Take sub-string from i to n-1
        suff = suff + str.charAt(i);

        // Print the sub-string
        System.out.print(suff);
    }
}

// Driver code
public static void main(String args[])
{
    String str = "geeks";
    printExpansion(str);

}
}
```

### Python 3

```python
# Python3 implementation of the approach

# Function to print the expansion
# of the string
def printExpansion( str):

    suff = ""
    for i in range (len (str) - 1, -1, -1) :

        # Take sub-string from i to n-1
        suff = suff + str[i]

        # Print the sub-string
        print (suff, end = "")

# Driver code
if __name__ == "__main__":

    str = "geeks"
    printExpansion(str)

# This code is contributed by ita_c
```

### C#

```csharp
// C# Implementation of the above approach
using System;

class GFG
{

// Function to print
// the expansion of the string
static void printExpansion(String str)
{
    String suff = "";
    for (int i = str.Length - 1;
             i >= 0; i--)
    {

        // Take sub-string from i to n-1
        suff = suff + str[i];

        // Print the sub-string
        Console.Write(suff);
    }
}

// Driver code
public static void Main(String []args)
{
    String str = "geeks";
    printExpansion(str);
}
}

// This code is contributed by PrinciRaj1992
```

### JavaScript

```javascript
<script>

// Javascript implementation of the approach

// Function to print the expansion of the string
function printExpansion(str)
{
    var suff = "";
    for (var i = str.length - 1; i >= 0; i--) {

        // Take sub-string from i to n-1
        suff = suff + str[i];

        // Print the sub-string
        document.write( suff);
    }
}

// Driver code
var str = "geeks";
printExpansion(str);

// This code is contributed by rrrtnx.
</script>
```

**输出:**

```
sskskeskeeskeeg
```