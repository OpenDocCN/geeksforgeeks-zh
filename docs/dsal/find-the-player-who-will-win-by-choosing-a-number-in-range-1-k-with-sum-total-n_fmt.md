# 通过选择范围[1，K]内的一个数字，并加上总数 N 来找到获胜的玩家

> 原文: [https://www.geeksforgeeks.org/find-the-player-who-will-win-by-choosing-a-number-in-range-1-k-with-sum-total-n/](https://www.geeksforgeeks.org/find-the-player-who-will-win-by-choosing-a-number-in-range-1-k-with-sum-total-n/)

给定两个整数 `K` 和 `N`，同时也给定 `Alice` 和 `Bob` 正在玩游戏。单次移动，玩家可以选择 `[1，K]` 范围内的一个数字，其数字使总数等于 `N` 的玩家获胜。打印 `Alice` 如果 `Alice` 赢了游戏，否则 `Bob`，如果 `Alice` 和 `Bob` 都交替且最优地玩游戏和 `Alice` 开始游戏。

**例:**

> **输入:** `K = 7`，`N = 8`
> **输出:** `Bob`
> **说明:** `Alice` 没有办法赢得比赛。当 `Alice` 从 1 到 7(包括 1 和 7)中选择任何一个数字时，对手在下一轮通过使总数为 8 赢得比赛。假设你选 5 号，对手选 3，赢了比赛，总比分是 `5+3=8`。
>
> **输入:** `K = 7`，`N = 50`
> **输出:** `Alice`

**进场:** 这个问题可以用[博弈论](https://www.geeksforgeeks.org/game-theory/)的概念来解决。观察**获胜状态**。这里要抓住的诀窍是 `Alice` 总是可以进行 `(K+1)` 重复的循环，无论 `Bob` 选择什么。假设在某个时刻 `Bob` 选择 `a`，`Alice` 可以选择 `[(K+1)-a]` 将选择保持在 `1` 到 `K` 的范围内，从而形成 `(K+1)` 的循环。现在 `Alice` 有了第一次机会，`Alice` 应该选择开始时 `N` 除以 `(K+1)` 剩下的余数，这样之后她就可以继续重复 `(K+1)` 的循环，达到总数为 `N`。
现在的观察是，如果 `N%(K+1)` 为 `0`，则是 `Alice` 不可能赢得比赛的唯一情况。
按照下面给出的步骤解决问题。

*   检查 `N%(K+1)` 是否为 `0`，打印 `Bob`。
*   在任何其他情况下，打印 `Alice`。

下面是上述方法的实现。

## C++

```cpp
// C++ program for above approach
#include <iostream>
using namespace std;

// Function to predict the winner
void predictTheWinner(int K, int N)
{

    if (N % (K + 1) == 0)
        cout << "Bob";
    else
        cout << "Alice";
}

// Driver Code
int main()
{

    // Given Input
    int K = 7, N = 50;

    // Function call
    predictTheWinner(K, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach

import java.io.*;

class GFG {

// Function to predict the winner
static void predictTheWinner(int K, int N)
{

    if (N % (K + 1) == 0)
         System.out.println( "Bob");
    else
         System.out.println("Alice");
}

// Driver Code
    public static void main (String[] args) {
        // Given Input
    int K = 7, N = 50;

    // Function call
    predictTheWinner(K, N);
    }
}
// This code is contributed by Potta Lokesh
```

## Python 3

```python
# Python 3 program for above approach

# Function to predict the winner
def predictTheWinner(K, N):
    if (N % (K + 1) == 0):
        print("Bob")
    else:
        print("Alice")

# Driver Code
if __name__ == '__main__':
    # Given Input
    K = 7
    N = 50

    # Function call
    predictTheWinner(K, N)

    # This code is contributed by SURENDRA_GANGWAR.
```

## C#

```csharp
// C# program for the above approach

using System;

public class GFG {

    // Function to predict the winner
    static void predictTheWinner(int K, int N)
    {

        if (N % (K + 1) == 0)
             Console.WriteLine( "Bob");
        else
             Console.WriteLine("Alice");
    }

    // Driver Code
    public static void Main (string[] args) {
        // Given Input
        int K = 7, N = 50;

        // Function call
        predictTheWinner(K, N);
    }
}

// This code is contributed by AnkThon
```

## JavaScript

```javascript
<script>

// javascript program for above approach

// Function to predict the winner
function predictTheWinner(K, N)
{

    if (N % (K + 1) == 0)
        document.write("Bob");
    else
        document.write("Alice");
}

// Driver Code
    // Given Input
    var K = 7, N = 50;

    // Function call
    predictTheWinner(K, N);

// This code is contributed by ipg2016107.
</script>
```

**Output:**

```
Alice
```

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`