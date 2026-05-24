# 披萨切割问题（或按线划圆）

> 原文：[https://www.geeksforgeeks.org/pizza-cut-problem-circle-division-lines/](https://www.geeksforgeeks.org/pizza-cut-problem-circle-division-lines/)

给定切割次数，找到可能的最大碎片数。

**例：**

```
Input  : 2
Output : 4

Input  : 3
Output : 7
```

## 问题分析与公式

这个问题无非是[懒人餐饮人的问题](https://www.geeksforgeeks.org/the-lazy-caterers-problem/)，并且有以下公式。

最大件数 = `1 + n*(n+1)/2`

参考[本](https://www.geeksforgeeks.org/the-lazy-caterers-problem/)进行证明。

## 代码实现

### C++

```cpp
// C++ program to find maximum no of pieces
// by given number of cuts
#include<bits/stdc++.h>
using namespace std;

// Function for finding maximum pieces
// with n cuts.
int findMaximumPieces(int n)
{
   return 1 + n*(n+1)/2;   
}

// Driver code
int main()
{
   cout << findMaximumPieces(3);
   return 0;
}
```

### Java

```java
// Java program to find maximum no of
// pieces by given number of cuts
class GFG {

    // Function for finding maximum pieces
    // with n cuts.
    static int findMaximumPieces(int n)
    {
        return 1 + n * (n + 1) / 2;
    }

    // Driver Program to test above function
    public static void main(String arg[])
    {

        System.out.print(findMaximumPieces(3));
    }
}

// This code is contributed by Anant Agarwal.
```

### Python 3

```python
# Python3 program to find maximum
# no. of pieces by given
# number of cuts

# Function for finding maximum
# pieces with n cuts.
def findMaximumPieces(n):
    return int(1 + n * (n + 1) / 2)

# Driver code
print(findMaximumPieces(3))

# This code is contributed 29AjayKumar
```

### C#

```csharp
// C# program to find maximum no of
// pieces by given number of cuts
using System;

class GFG {

    // Function for finding maximum pieces
    // with n cuts.
    static int findMaximumPieces(int n)
    {
        return 1 + n * (n + 1) / 2;
    }

    // Driver Program to test above function
    public static void Main()
    {

        Console.Write(findMaximumPieces(3));
    }
}

// This code is contributed by nitin mittal.
```

### PHP

```php
<?php
// PHP program to find maximum
// no. of pieces by given
// number of cuts

// Function for finding maximum
// pieces with n cuts.
function findMaximumPieces($n)
{
    return 1 + $n * ($n + 1) / 2;
}

// Driver code
echo findMaximumPieces(3);

// This code is contributed by nitin mittal.
?>
```

### JavaScript

```javascript
<script>

// Javascript program to find maximum no of pieces
// by given number of cuts

// Function for finding maximum pieces
 // with n cuts.
    function findMaximumPieces(n)
    {
        return 1 + n * (n + 1) / 2;
    }

// Driver Code

    document.write(findMaximumPieces(3));

</script>
```

**输出：**

```
7
```

本文由**丹麦语 _RAZA** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。