# 通过移除最后一张给定的 N 张牌找到赢得游戏的玩家

> 原文: [https://www.geeksforgeeks.org/find-the-player-who-wins-the-game-by-removing-the-last-of-given-n-cards/](https://www.geeksforgeeks.org/find-the-player-who-wins-the-game-by-removing-the-last-of-given-n-cards/)

## 问题描述

给定两个整数 `N` 和 `K`，其中 `N` 表示游戏开始时出现的牌总数，`K` 表示单回合可以移除的最大牌数。两名玩家 `A` 和 `B` 轮流最多移除 `K` 张牌，从玩家 `A` 开始逐一移除，移除最后一张牌的玩家即为赢家。任务是检查 `A` 能否赢得比赛。如果发现是真的，打印 `'A'` 作为答案。否则，打印 `'B'`。

## 示例

**输入:** `N = 14`，`K = 10`
**输出:** 是
**说明:**
回合 1: `A` 第一回合移除 3 张牌。
第 2 回合: `B` 从范围【1–10】中移除任意数量的牌，最后 `A` 可以移除所有剩余牌并赢得游戏，因为第 2 回合后剩余牌的数量将 ≤ 10

**输入:** `N = 11`，`K = 10`
**输出:** 否

## 思路

这里的思路是观察每当 `N % (K + 1) = 0` 时，那么 `A` 将永远无法赢得比赛。否则 `A` 永远赢不了比赛。

## 证明

1.  如果 `N ≤ K`：拥有第一回合的人将赢得游戏，即 `A`。
2.  如果 `n = k+1`：`A` 可以在 `[1, k]` 的范围内移除任意数量的牌。所以第一回合后剩余的牌总数也在 `[1, k]` 的范围内。`B` 现在获得回合，剩余的牌数在 `[1, k]` 的范围内。所以，`B` 将赢得游戏。
3.  如果 `K+2 ≤ N ≤ 2K+1`：`A` 在第一回合移除 `N - (K+1)` 张牌。`B` 在下一回合可以在 `[1, k]` 的范围内移除任意数量的牌。所以现在剩余的牌总数在 `[1, k]` 的范围内。现在，由于剩余的牌在 `[1, k]` 的范围内，`A` 可以移除所有的牌并赢得游戏。

所以思路是检查 `N % (K + 1)` 是否等于 0。如果发现是真的，打印 `B` 作为获胜者。否则，打印 `A` 作为获胜者。

## 代码实现

以下是上述办法的实施情况:

### C++

```cpp
// C++ Program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check which
// player can win the game
void checkWinner(int N, int K)
{
    if (N % (K + 1)) {
        cout << "A";
    }
    else {
        cout << "B";
    }
}

// Driver code
int main()
{

    int N = 50;
    int K = 10;
    checkWinner(N, K);
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG{

// Function to check which
// player can win the game
static void checkWinner(int N, int K)
{
    if (N % (K + 1) > 0)
    {
        System.out.print("A");
    }
    else
    {
        System.out.print("B");
    }
}

// Driver code
public static void main(String[] args)
{
    int N = 50;
    int K = 10;

    checkWinner(N, K);
}
}

// This code is contributed by Amit Katiyar
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to check which
# player can win the game
def checkWinner(N, K):

    if(N % (K + 1)):
        print("A")
    else:
        print("B")

# Driver Code
N = 50
K = 10

# Function call
checkWinner(N, K)

# This code is contributed by Shivam Singh
```

### C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to check which
// player can win the game
static void checkWinner(int N, int K)
{
    if (N % (K + 1) > 0)
    {
        Console.Write("A");
    }
    else
    {
        Console.Write("B");
    }
}

// Driver code
public static void Main(String[] args)
{
    int N = 50;
    int K = 10;

    checkWinner(N, K);
}
}

// This code is contributed by Amit Katiyar
```

### JavaScript

```javascript
<script>
    // Javascript Program to implement
// the above approach

// Function to check which
// player can win the game
function checkWinner(N, K)
{
    if (N % (K + 1)) {
        document.write("A");
    }
    else {
        document.write("B");
    }
}

// Driver code

    let N = 50;
    let K = 10;
    checkWinner(N, K);

// This code is contributed by Saurabh Jaiswal
</script>
```

**输出:**

```
A
```

`时间复杂度:` O(1)
`辅助空间:` O(1)