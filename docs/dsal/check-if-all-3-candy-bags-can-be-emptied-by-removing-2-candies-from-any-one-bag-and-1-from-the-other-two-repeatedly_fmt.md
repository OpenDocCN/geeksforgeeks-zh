# 通过重复从任何一个糖果袋中取出 2 个糖果，从另外两个糖果袋中取出 1 个糖果，检查是否所有 3 个糖果袋都可以清空

> 原文: [https://www.geeksforgeeks.org/check-if-all-3-candy-bags-can-be-emptied-by-removing-2-candies-from-any-one-bag-and-1-from-the-other-two-repeatedly/](https://www.geeksforgeeks.org/check-if-all-3-candy-bags-can-be-emptied-by-removing-2-candies-from-any-one-bag-and-1-from-the-other-two-repeatedly/)

给定 3 个整数 `a`、`b` 和 `c`，表示三个袋子中糖果的数量。你需要找到我们是否可以通过执行一个特定的操作来清空所有的袋子，在每个操作中，你可以从一个袋子中吃 `2` 糖果，从另两个袋子中吃 `1` 糖果。不允许跳过任何一袋，即每次操作必须从每袋中吃 1 或 2 颗糖果。如果可能，返回真，否则返回假。

## 示例

> **输入:** 4、2、2
> **输出:** 真
> **说明:**
> **操作 1** : 你可以吃到袋 1 的 2 颗糖果和袋 2、袋 3 的 1 颗糖果。
> 手术后留下的糖果 1
> *袋 1* = `2`、*袋 2* = `1`、*袋 3* = `1`
> **操作 2**: 你可以吃袋 1 的 2 颗糖果，每个袋 2 和袋 3 的 1 颗
> 手术后留下的糖果 2
> *袋 1* = `0`、*袋 2* = `0`、*袋 3* = `0`
>
> **输入:** 3、4、2
> **输出:** 假

## 方法分析

**天真方法:** 迭代变量，直到三个变量都不变成 0。在每次迭代中，最大元素减少 2，剩余变量减少 1。

**时间复杂度:** `O(N)`，其中 `N` 为 `a`、`b` 和 `c` 的最大变量值

**有效方法**: 通过进行以下观察，可以用有效方法解决给定的问题:

*   在每个操作中，我们将选择 1+2+1=4 颗糖果，因此袋 1、袋 2 和袋 3 中所有糖果的总和必须被 `4` 整除。
*   清空所有袋子所需的操作次数为 `(所有糖果的总和)/4`。
*   在任何操作中，我们必须从一个袋子中挑选 1 或 2 颗糖果，因此 3 个袋子中存在的最小糖果数必须大于或等于操作数。

## 代码实现

### C++

```cpp
// C++ code for the above approach

#include <bits/stdc++.h>
#define ll long long
using namespace std;

bool can_empty(ll a, ll b, ll c)
{
    // If total candies are not multiple
    // of 4 then its not possible to be
    // left with 0 candies
    if ((a + b + c) % 4 != 0)
        return false;
    else {

        // If minimum candies of three bags
        // are less than number of operations
        // required then the task is not possible
        int m = min(a, min(b, c));
        if (m < ((a + b + c) / 4))
            return false;
    }
    return true;
}

// Driver code
int main()
{
    ll a = 4, b = 2, c = 2;
    cout << (can_empty(a, b, c) ? "true" : "false")
         << endl;

    a = 3, b = 4, c = 2;
    cout << (can_empty(a, b, c) ? "true" : "false")
         << endl;

    return 0;
}
```

### Java

```java
// Java code for the above approach
import java.util.*;

class GFG{

static boolean can_empty(int a, int b, int c)
{

    // If total candies are not multiple
    // of 4 then its not possible to be
    // left with 0 candies
    if ((a + b + c) % 4 != 0)
        return false;
    else
    {

        // If minimum candies of three bags
        // are less than number of operations
        // required then the task is not possible
        int m = Math.min(a, Math.min(b, c));
        if (m < ((a + b + c) / 4))
            return false;
    }
    return true;
}

// Driver Code
public static void main(String[] args)
{
    int a = 4, b = 2, c = 2;
    System.out.println(can_empty(a, b, c) ?
                       "true" : "false");

    a = 3;
    b = 4;
    c = 2;
    System.out.println(can_empty(a, b, c) ?
                       "true" : "false");
}
}

// This code is contributed by code_hunt
```

### Python 3

```python
# Python code for the above approach
def can_empty(a, b, c):

    # If total candies are not multiple
    # of 4 then its not possible to be
    # left with 0 candies
    if ((a + b + c) % 4 != 0) :
        return False;
    else :

        # If minimum candies of three bags
        # are less than number of operations
        # required then the task is not possible
        m = min(a, min(b, c));
        if (m < (a + b + c) // 4) :
            return False;

    return True;

# Driver code
a = 4
b = 2
c = 2
print("true" if can_empty(a, b, c) else "false");

a = 3
b = 4
c = 2
print("true" if can_empty(a, b, c) else "false");

# This code is contributed by _saurabh_jaiswal
```

### C#

```csharp
using System;

public class GFG {
    static bool can_empty(int a, int b, int c)
    {

        // If total candies are not multiple
        // of 4 then its not possible to be
        // left with 0 candies
        if ((a + b + c) % 4 != 0)
            return false;
        else {

            // If minimum candies of three bags
            // are less than number of operations
            // required then the task is not possible
            int m = Math.Min(a, Math.Min(b, c));
            if (m < ((a + b + c) / 4))
                return false;
        }
        return true;
    }

    // Driver Code
    static public void Main()
    {
        int a = 4, b = 2, c = 2;
        Console.WriteLine(can_empty(a, b, c) ? "true"
                                              : "false");

        a = 3;
        b = 4;
        c = 2;
        Console.WriteLine(can_empty(a, b, c) ? "true"
                                              : "false");
    }
}

// This code is contributed by maddler.
```

### JavaScript

```javascript
<script>

// Javascript code for the above approach
function can_empty(a, b, c)
{

    // If total candies are not multiple
    // of 4 then its not possible to be
    // left with 0 candies
    if ((a + b + c) % 4 != 0)
        return false;
    else
    {

        // If minimum candies of three bags
        // are less than number of operations
        // required then the task is not possible
        let m = Math.min(a, Math.min(b, c));
        if (m < Math.floor((a + b + c) / 4))
            return false;
    }
    return true;
}

// Driver code
let a = 4,
b = 2,
c = 2;
document.write(can_empty(a, b, c) ? "true" : "false");
document.write("<br>");

(a = 3), (b = 4), (c = 2);
document.write(can_empty(a, b, c) ? "true" : "false");

// This code is contributed by _saurabh_jaiswal

</script>
```

**Output:**

```
true
false
```

## 复杂度分析

*   **时间复杂度:** `O(1)`
*   **空间复杂度:** `O(1)`