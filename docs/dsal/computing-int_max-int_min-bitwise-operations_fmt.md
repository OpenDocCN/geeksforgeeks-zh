## 通过逐位运算计算 INT_MAX 和 INT_MIN

> 原文: [https://www.geeksforgeeks.org/computing-int_max-int_min-bitwise-operations/](https://www.geeksforgeeks.org/computing-int_max-int_min-bitwise-operations/)

### 先决条件:
[C/C++中的 `INT_MAX` 和 `INT_MIN` 及其应用。](https://www.geeksforgeeks.org/int_max-int_min-cc-applications/)
0 和 1 分别代表符号位所在的最高有效位位置。

### 计算 C/C++ 中的 `INT_MAX` 和 `INT_MIN`:
数字 0 表示为 **000…000** (32 次)。

*   我们计算 0 的 **NOT** 得到一个有 32 个 1 的数。这个数字不等于 `INT_MAX`，因为符号位是 1，即负数。
*   现在，这个数字的右移会产生 **011…111** ，也就是 `INT_MAX`。
*   整数最小值不是整数最大值。

**注:**
0 应取无符号整数。
**原因:**
如果 0 被声明为有符号类型，在步骤 2 期间，右移 `111..111` 将产生 `111…111`。这是因为算术右移保留了数字的符号。
在 Java 中，我们拥有逻辑右移的特性。

### C++
```cpp
// CPP code to compute INT_MAX and INT_MIN using
// bitwise operations
#include <bits/stdc++.h>
using namespace std;

void printMinMaxValues()
{
    // 0 saved as unsigned int
    unsigned int max = 0;

    // Computing NOT of 0
    max = ~max;

    // 1 time arithmetic right shift
    max = max >> 1;

    // Computing INT_MIN
    int min = max;

    // INT_MIN = ~INT_MAX
    min = ~min;

    // Printing the result
    cout << "INT_MAX : " << max
         << " INT_MIN : " << min;
}

// Driver code
int main()
{
    printMinMaxValues();
    return 0;
}
```

### Java
```java
// Java code to compute INT_MAX and INT_MIN using
// bitwise operations
public class Solution
{
    static void printMinMaxValues()
    {
        int max = 0;

        // Computing NOT of 0
        max = ~max;

        // 1 time logical right shift for INT_MAX
        max = max >>> 1;

        // Computing INT_MIN
        int min = max;

        // INT_MIN = ~INT_MAX
        min = ~max;

        // Printing the result
        System.out.println("INT_MAX " + max +
                           " INT_MIN " + min);
    }

    public static void main(String[] args)
    {
        printMinMaxValues();
    }
}
```

### JavaScript
```javascript
// Javascript code to compute INT_MAX and INT_MIN using
// bitwise operations

function printMinMaxValues()
{
    let max = 0;

    // Computing NOT of 0
    max = ~max;

    // 1 time logical right shift for INT_MAX
    max = max >>> 1;

    // Computing INT_MIN
    let min = max;

    // INT_MIN = ~INT_MAX
    min = ~max;

    // Printing the result
    document.write("INT_MAX - " + max +
                   ", INT_MIN " + min);
}

// driver program
printMinMaxValues();

// This code is contributed by code_hunt.
```

### 输出:
```
INT_MAX 2147483647 INT_MIN -2147483648
```

问于: [谷歌](https://practice.geeksforgeeks.org/company/Google/)
本文由 [**罗希特·塔普利亚尔**](https://www.hackerrank.com/rohit_thapliyal) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。