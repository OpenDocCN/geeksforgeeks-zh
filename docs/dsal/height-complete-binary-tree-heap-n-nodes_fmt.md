# 具有 N 个节点的完整二叉树(或堆)的高度

> 原文: [https://www.geeksforgeeks.org/height-complete-binary-tree-heap-n-nodes/](https://www.geeksforgeeks.org/height-complete-binary-tree-heap-n-nodes/)

考虑一个 `N` 大小的[二进制堆](https://www.geeksforgeeks.org/binary-heap/)，我们需要找到它的高度。

**例:**

```
Input : N = 6
Output : 2
        ()
      /    \
     ()     ()
    /  \    /
  ()    () ()

Input : N = 9
Output :
        ()
      /    \
     ()     ()
    /  \    /  \
  ()    () ()   ()
 / \
()  ()
```

让堆的大小为 `N`，高度为 `h`。举几个例子，我们可以注意到一个[完全二叉树](https://www.geeksforgeeks.org/binary-tree-set-3-types-of-binary-tree/)中 `h` 的值是 `ceil(log2(N+1))–1`。

示例:

```
 N    h

 1    0
 2    1
 3    1
 4    2
 5    2
 .....
 .....
```

## C++

```cpp
// CPP program to find height of complete
// binary tree from total nodes.
#include <bits/stdc++.h>
using namespace std;

int height(int N)
{
    return ceil(log2(N + 1)) - 1;
}

// driver node
int main()
{
    int N = 6;
    cout << height(N);
    return 0;
}
```

## Java

```java
// Java program to find height
// of complete binary tree
// from total nodes.
import java.lang.*;

class GFG {

    // Function to calculate height
    static int height(int N)
    {
        return (int)Math.ceil(Math.log(N +
                    1) / Math.log(2)) - 1;
    }

    // Driver Code
    public static void main(String[] args)
    {
        int N = 6;
        System.out.println(height(N));
    }
}

// This code is contributed by
// Smitha Dinesh Semwal
```

## Python 3

```python
# Python 3 program to find
# height of complete binary
# tree from total nodes.
import math
def height(N):
    return math.ceil(math.log2(N + 1)) - 1

# driver node
N = 6
print(height(N))

# This code is contributed by
# Smitha Dinesh Semwal
```

## C#

```csharp
// C# program to find height
// of complete binary tree
// from total nodes.
using System;

class GFG {
    static int height(int N)
    {
        return (int)Math.Ceiling(Math.Log(N
                   + 1) / Math.Log(2)) - 1;
    }

    // Driver node
    public static void Main()
    {
        int N = 6;
        Console.Write(height(N));
    }
}

// This code is contributed by
// Smitha Dinesh Semwal
```

## PHP

```php
<?php
// PHP program to find height
// of complete binary tree
// from total nodes.

function height($N)
{
    return ceil(log($N + 1, 2)) - 1;
}

// Driver Code
$N = 6;
echo height($N);

// This code is contributed by aj_36
?>
```

## JavaScript

```javascript
<script>

    // Javascript program to find height
    // of complete binary tree
    // from total nodes.

    function height(N)
    {
        return Math.ceil(Math.log(N + 1) / Math.log(2)) - 1;
    }

      let N = 6;
      document.write(height(N));

</script>
```

**Output :**

```
2
```