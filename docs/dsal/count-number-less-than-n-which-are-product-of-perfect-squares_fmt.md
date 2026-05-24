# 计算小于 N 的完美正方形的乘积

> 原文：[https://www.geeksforgeeks.org/count-number-less-than-n-which-are-product-of-perfect-squares/](https://www.geeksforgeeks.org/count-number-less-than-n-which-are-product-of-perfect-squares/)

给定一个整数 `N`，任务是计算小于 `N` 的数 `P`，使得 `P` 是两个不同的完美平方的乘积。

**例**：

```
Input : N = 36
Output : 5
Numbers are 4 = 1^2 * 2^2, 
9 = 1^2 * 3^2, 
16 = 1^2 * 4^2, 
25 = 1^2 * 5^2, 
36 = 1^2 * 6^2

Input : N = 1000000
Output : 999
```

## 方法

让我们考虑一个数字 `P = (a^2 * b^2)` 这样 `P <= N`。所以我们有 `(a^2 * b^2) <= N`，这可以写成 `(a * b) <= sqrt(N)`。
所以我们要对 `(a, b)` 进行计数，这样 `(a * b) <= sqrt(N)` 和 `a <= b`。
让我们取一个数 `Q = (a * b)` 这样 `Q <= sqrt(N)`。
取 `a = 1`，我们有 `b = sqrt(N) - 1` 个数字，这样 `(a * b = Q <= sqrt(N))`。
因此我们可以拥有所有 `sqrt(N) - 1` 的数字，这样 `(a^2 * b^2) <= N`。

以下是上述方法的实现：

### C++

```cpp
// C++ program to count number less
// than N which are product of
// any two perfect squares

#include <bits/stdc++.h>
using namespace std;

// Function to count number less
// than N which are product of
// any two perfect squares
int countNumbers(int N)
{
    return int(sqrt(N)) - 1;
}

// Driver program
int main()
{
    int N = 36;

    cout << countNumbers(N);

    return 0;
}
```

### Java

```java
// Java program to count number less
// than N which are product of
// any two perfect squares
import java.util.*;

class solution
{

// Function to count number less
// than N which are product of
// any two perfect squares
static int countNumbers(int N)
{
    return (int)Math.sqrt(N) - 1;
}

// Driver program
public static void main(String args[])
{
    int N = 36;

    System.out.println(countNumbers(N));

}

}

//This code is contributed by
// Surendra_Gangwar
```

### Python 3

```python
# Python 3 program to count number
# less than N which are product of
# any two perfect squares
import math

# Function to count number less
# than N which are product of
# any two perfect squares
def countNumbers(N):
    return int(math.sqrt(N)) - 1

# Driver Code
if __name__ == "__main__":
    N = 36

    print(countNumbers(N))

# This code is contributed
# by ChitraNayal
```

### C#

```csharp
// C# program to count number less
// than N which are product of
// any two perfect squares
using System;

class GFG
{
// Function to count number less
// than N which are product of
// any two perfect squares
static int countNumbers(int N)
{
    return (int)(Math.Sqrt(N)) - 1;
}

// Driver Code
public static void Main()
{
    int N = 36;

    Console.Write(countNumbers(N));
}
}

// This code is contributed
// by Akanksha Rai
```

### PHP

```php
<?php
// PHP program to count number less
// than N which are product of
// any two perfect squares

// Function to count number less
// than N which are product of
// any two perfect squares
function countNumbers($N)
{
    return (int)(sqrt($N)) - 1;
}

// Driver Code
$N = 36;
echo countNumbers($N);

// This code is contributed by akt_mit
?>
```

### JavaScript

```javascript
<script>
    // Javascript program to count number less
    // than N which are product of
    // any two perfect squares

    // Function to count number less
    // than N which are product of
    // any two perfect squares
    function countNumbers(N)
    {
        return parseInt(Math.sqrt(N), 10) - 1;
    }

    let N = 36;

    document.write(countNumbers(N));

</script>
```

**Output:**

```
5
```

**时间复杂度:** O(log(N))