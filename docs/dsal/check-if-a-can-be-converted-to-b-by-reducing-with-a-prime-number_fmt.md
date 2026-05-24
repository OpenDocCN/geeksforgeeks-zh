# 用质数减，检查 A 是否能转化为 B

> 原文: [https://www.geeksforgeeks.org/check-if-a-can-be-converted-to-b-by-reducing-with-a-prime-number/](https://www.geeksforgeeks.org/check-if-a-can-be-converted-to-b-by-reducing-with-a-prime-number/)

给定两个整数 `A` 和 `B`，任务是：如果允许你从 `A` 中减去一个[质数](https://www.geeksforgeeks.org/prime-numbers/) `P` 任意次数，是否可以让 `A` 等于 `B`。

**举例:**

> **输入:** `A = 10`，`B = 4`
> **输出:** 是
> **解释:**
> 让 `P = 2`，从 `A` 中减去三次。
>
> **输入:** `A = 41`，`B = 40`
> **输出:** 否

### 方法

问题中的关键观察是我们必须将数字 `A` 表示为 `A = B + X * P`。

正如我们所知，除了 1，每个数都可以被某个素数整除。因此，如果我们找到了数的差 `A - B`，如果差值大于 1，则可以通过从 `A` 中减去质数 `X` 倍来使两个数相等。

下面是上述方法的实现:

## C++

```cpp
// C++ implementation to find if
// it is possible to make a equal to b

#include <bits/stdc++.h>
using namespace std;

// Function to find if
// it is possible to make
// A equal to B
bool isPossible(int A, int B)
{
    return (A - B > 1);
}

// Driver Code
int main()
{
    int A = 10, B = 4;

    // Function Call
    if (isPossible(A, B))
        cout << "Yes";
    else
        cout << "No";
    return 0;
}
```

## Java

```java
// Java implementation to find if
// it is possible to make a equal to b
class GFG{

// Function to find if
// it is possible to make
// A equal to B
static boolean isPossible(int A, int B)
{
    return (A - B > 1);
}

// Driver Code
public static void main (String[] args)
{
    int A = 10, B = 4;

    // Function Call
    if (isPossible(A, B))
        System.out.print("Yes");
    else
        System.out.print("No");
}
}

// This code is contributed by shivanisinghss2110
```

## Python 3

```python
# Python3 implementation to find if
# it is possible to make a equal to b

# Function to find if
# it is possible to make
# A equal to B
def isPossible(A, B):

    return (A - B > 1);

# Driver Code
A = 10; B = 4;

# Function Call
if (isPossible(A, B)):
    print("Yes");
else:
    print("No");

# This code is contributed by Code_Mech
```

## C#

```csharp
// C# implementation to find if
// it is possible to make a equal to b
using System;
class GFG{

// Function to find if
// it is possible to make
// A equal to B
static bool isPossible(int A, int B)
{
    return (A - B > 1);
}

// Driver Code
public static void Main()
{
    int A = 10, B = 4;

    // Function Call
    if (isPossible(A, B))
        Console.Write("Yes");
    else
        Console.Write("No");
}
}

// This code is contributed by Code_Mech
```

## JavaScript

```javascript
<script>

    // Javascript implementation to find if
    // it is possible to make a equal to b

    // Function to find if
    // it is possible to make
    // A equal to B
    function isPossible(A, B)
    {
        return (A - B > 1);
    }

    let A = 10, B = 4;

    // Function Call
    if (isPossible(A, B))
        document.write("Yes");
    else
        document.write("No");

</script>
```

**Output:** Yes