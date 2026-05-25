# 带交替符号的前 N 个自然数之和

> 原文: [https://www.geeksforgeeks.org/sum-of-first-n-natural-numbers-with-alternate-signs/](https://www.geeksforgeeks.org/sum-of-first-n-natural-numbers-with-alternate-signs/)

给定一个整数 `N`，任务是求第一个带有交替符号的 `N` 自然数的和，即 `1–2+3–4+5–6+…`。

## 示例

> **输入:** `N = 6`
> **输出:** -3
> **解释:**
> `1–2+3–4+5–6 = -3`
> 因此，所需输出为 -3。
>
> **输入:** `N = 5`
> **输出:** 3
> **说明:**
> `1–2+3–4+5 = 3`
> 因此，所需输出 = 3

## 天真方法

按照以下步骤解决问题:

*   初始化一个变量，说 `alternateSum` 存储第一个 `N` 自然数的交替符号的和。
*   使用变量 `i` 和在范围 `[1, N]` 内迭代，检查 `i` 是否为偶数。如果发现为真，则更新 `alternateSum += -i`。
*   否则，更新 `alternateSum += i`。
*   最后，打印 `alternateSum` 的值。

下面是上述方法的实现:

### C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the sum of first
// N natural numbers with alternate signs
int alternatingSumOfFirst_N(int N)
{
    // Stores sum of alternate sign
    // of first N natural numbers
    int alternateSum = 0;

    for (int i = 1; i <= N; i++) {

        // If is an even number
        if (i % 2 == 0) {

            // Update alternateSum
            alternateSum += -i;
        }

        // If i is an odd number
        else {

            // Update alternateSum
            alternateSum += i;
        }
    }
    return alternateSum;

}

// Driver Code
int main()
{

    int N = 6;
    cout<<alternatingSumOfFirst_N(N);
    return 0;
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG{

// Function to find the sum of first
// N natural numbers with alternate signs
static int alternatingSumOfFirst_N(int N)
{

    // Stores sum of alternate sign
    // of first N natural numbers
    int alternateSum = 0;

    for(int i = 1; i <= N; i++)
    {

        // If is an even number
        if (i % 2 == 0)
        {

            // Update alternateSum
            alternateSum += -i;
        }

        // If i is an odd number
        else
        {

            // Update alternateSum
            alternateSum += i;
        }
    }
    return alternateSum;
}

// Driver Code
public static void main(String[] args)
{
    int N = 6;

    System.out.print(alternatingSumOfFirst_N(N));
}
}

// This code is contributed by Amit Katiyar
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to find the sum of
# First N natural numbers with
# alternate signs
def alternatingSumOfFirst_N(N):

    # Stores sum of alternate sign
    # of First N natural numbers
    alternateSum = 0

    for i in range(1, N + 1):

        # If is an even number
        if (i % 2 == 0):

            # Update alternateSum
            alternateSum += -i

        # If i is an odd number
        else:
            alternateSum += i

    return alternateSum

# Driver Code
if __name__ == "__main__" :

    N = 6

    print(alternatingSumOfFirst_N(N))

# This code is contributed by Virusbuddah_
```

### C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG{

// Function to find the sum of first
// N natural numbers with alternate signs
static int alternatingSumOfFirst_N(int N)
{

    // Stores sum of alternate sign
    // of first N natural numbers
    int alternateSum = 0;

    for(int i = 1; i <= N; i++)
    {

        // If is an even number
        if (i % 2 == 0)
        {

            // Update alternateSum
            alternateSum += -i;
        }

        // If i is an odd number
        else
        {

            // Update alternateSum
            alternateSum += i;
        }
    }
    return alternateSum;
}

// Driver Code
public static void Main(String[] args)
{
    int N = 6;

    Console.Write(alternatingSumOfFirst_N(N));
}
}

// This code is contributed by 29AjayKumar
```

### JavaScript

```javascript
<script>

// Javascript program to implement
// the above approach

    // Function to find the sum of first
    // N natural numbers with alternate signs
    function alternatingSumOfFirst_N(N)
    {

        // Stores sum of alternate sign
        // of first N natural numbers
        var alternateSum = 0;

        for (i = 1; i <= N; i++) {

            // If is an even number
            if (i % 2 == 0) {

                // Update alternateSum
                alternateSum += -i;
            }

            // If i is an odd number
            else {

                // Update alternateSum
                alternateSum += i;
            }
        }
        return alternateSum;
    }

    // Driver Code

        var N = 6;

        document.write(alternatingSumOfFirst_N(N));

// This code is contributed by Rajput-Ji

</script>
```

**输出:**

```
-3
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`

## 高效方法

为了优化上述方法，该想法基于以下观察:

> 如果 `N` 是偶数，那么前 `N` 个自然数的交替符号之和为 `= (-N) / 2`。
>
> 如果 `N` 是奇数，那么前 `N` 个自然数的交替符号之和为 `= (N + 1) / 2`。

按照以下步骤解决问题:

*   初始化一个变量，说 `alternateSum` 存储第一个 `N` 自然数的交替符号的和。
*   检查 `N` 是否为偶数。如果发现为真，则更新 `alternateSum = (-N) / 2`。
*   否则，更新 `alternateSum = (N + 1) / 2`。
*   最后，打印 `alternateSum` 的值。

下面是上述方法的实现:

### C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the sum of first
// N natural numbers with alternate signs
int alternatingSumOfFirst_N(int N)
{
    // Stores sum of alternate sign
    // of first N natural numbers
    int alternateSum = 0;

    // If N is an even number
    if (N % 2 == 0) {

        // Update alternateSum
        alternateSum = (-N) / 2;
    }

    // If N is an odd number
    else {
        // Update alternateSum
        alternateSum = (N + 1) / 2;
    }
    return alternateSum;
}

// Driver Code
int main()
{

    int N = 6;
    cout<<alternatingSumOfFirst_N(N);
    return 0;
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG
{

// Function to find the sum of first
// N natural numbers with alternate signs
static int alternatingSumOfFirst_N(int N)
{
    // Stores sum of alternate sign
    // of first N natural numbers
    int alternateSum = 0;

    // If N is an even number
    if (N % 2 == 0)
    {

        // Update alternateSum
        alternateSum = (-N) / 2;
    }

    // If N is an odd number
    else
    {

        // Update alternateSum
        alternateSum = (N + 1) / 2;
    }
    return alternateSum;
}

// Driver Code
public static void main(String[] args)
{
    int N = 6;
    System.out.print(alternatingSumOfFirst_N(N));
}
}

// This code is contributed by 29AjayKumar
```

### Python 3

```python
# Python program to implement
# the above approach

# Function to find the sum of first
# N natural numbers with alternate signs
def alternatingSumOfFirst_N(N):

    # Stores sum of alternate sign
    # of first N natural numbers
    alternateSum = 0;

    # If N is an even number
    if (N % 2 == 0):

        # Update alternateSum
        alternateSum = (-N) // 2;

    # If N is an odd number
    else:

        # Update alternateSum
        alternateSum = (N + 1) // 2;

    return alternateSum;

# Driver Code
if __name__ == '__main__':
    N = 6;
    print(alternatingSumOfFirst_N(N));

# This code contributed by shikhasingrajput
```

### C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG
{

// Function to find the sum of first
// N natural numbers with alternate signs
static int alternatingSumOfFirst_N(int N)
{
    // Stores sum of alternate sign
    // of first N natural numbers
    int alternateSum = 0;

    // If N is an even number
    if (N % 2 == 0)
    {

        // Update alternateSum
        alternateSum = (-N) / 2;
    }

    // If N is an odd number
    else
    {

        // Update alternateSum
        alternateSum = (N + 1) / 2;
    }
    return alternateSum;
}

// Driver Code
public static void Main(String[] args)
{
    int N = 6;
    Console.Write(alternatingSumOfFirst_N(N));
}
}

// This code is contributed by 29AjayKumar
```

## java 描述语言

```javascript
<script>

// Javascript program to implement
// the above approach

    // Function to find the sum of first
    // N natural numbers with alternate signs
    function alternatingSumOfFirst_N(N)
    {
        // Stores sum of alternate sign
        // of first N natural numbers
        var alternateSum = 0;

        // If N is an even number
        if (N % 2 == 0) {

            // Update alternateSum
            alternateSum = (-N) / 2;
        }

        // If N is an odd number
        else {

            // Update alternateSum
            alternateSum = (N + 1) / 2;
        }
        return alternateSum;
    }

    // Driver Code

        var N = 6;
        document.write(alternatingSumOfFirst_N(N));

// This code contributed by Rajput-Ji

</script>
```

`Output:`

```

```

`时间复杂度:` `O(1)`
`辅助空间:` `O(1)`