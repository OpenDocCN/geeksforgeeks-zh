# 在 N 球游戏中寻找赢家，玩家可以在单次移动中移除范围 [A, B] 内的任何球

> 原文: [https://www.geeksforgeeks.org/find-winner-in-game-of-n-balls-in-which-a-player-can-remove-any-balls-in-range-a-b-in-a-single-move/](https://www.geeksforgeeks.org/find-winner-in-game-of-n-balls-in-which-a-player-can-remove-any-balls-in-range-a-b-in-a-single-move/)

给定两个整数 `A` 和 `B`，并且还给定爱丽丝和鲍勃正在玩一个从包含 `N` 个球的袋子开始的游戏，其中，在单次移动中，玩家可以移除范围 `[A, B]` 之间的任意数量的球，并且如果玩家不能移除任何球，则玩家输了，任务是如果爱丽丝和鲍勃交替并且最优地玩游戏并且爱丽丝开始游戏，则找到游戏的赢家。

## 示例

> **输入:** `N = 2`，`A = 1`，`B = 1`
> **输出:** 鲍勃
> **解释:**
> 可以玩游戏的一种方式是:
> 1.  爱丽丝移除 1 个球，所以剩下的球是 1 个。
> 2.  现在，鲍勃拿走了最后一个球。
> 3.  爱丽丝不能取出任何球，所以她输了。
>
> **输入:** `N = 3`，`A = 1`，`B = 2`
> **输出:** 鲍勃

## 天真法

最简单的方法就是利用[斯普拉格-格鲁迪定理](https://www.geeksforgeeks.org/combinatorial-game-theory-set-4-sprague-grundy-theorem/?ref=rp)找到每个州的[格鲁迪数](https://www.geeksforgeeks.org/combinatorial-game-theory-set-3-grundy-numbersnimbers-and-mex/)并找到输赢州。

时间复杂度: `O(N*N!)`
辅助空间: `O(N)`

## 高效方法

上述方法可以基于以下观察进行优化:

1.  首先，我们可以观察到 `(a+b)` 总是处于失败状态，因为无论玩家当前选择多少个球 `x` (`a ≤ x ≤ b`)，对手总是可以清空袋子，因为袋子里会剩下 `(a+b–x)` 个球。
2.  类似地，从上一个观察可以推断，对于 `(a+b)` 的任何倍数，例如 `m * (a+b)`，对手总是可以将当前玩家降低到 `(m–1) * (a+b)` 的状态。
3.  因此，扩展上述观察，可以说对于 `(a+b)` 的任何倍数，对手总是可以将当前玩家降低到一个类似于 `(a+b)` 的状态，这确实是一个失败状态。因此，所有 `(a+b)` 的倍数都处于失败状态。
4.  因此，任何玩家的最佳选择是将对手降低到 `(a+b)` 的倍数，因为在此之后，无论对手如何移动，玩家总是可以获胜。
5.  因此，现在的失败状态是一个永远无法将对手降低到 `(a+b)` 倍数的状态。
6.  因此，任何状态为 `((a+b) * m + y)` 的玩家，其中 `(0 ≤ y ≤ a-1)`，永远无法迫使对手降低到 `(a+b)` 的倍数，只能被任何玩家至少选择一次。

## 按照以下步骤解决问题

*   如果 `N % (A+B)` 小于 `A`，则打印“鲍勃”。
*   否则，打印“爱丽丝”。

## 下面是上述方法的实现

### C++

```cpp
// C++ program of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the winner of the
// game
string NimGame(int N, int A, int B)
{
    // Stores sum of A and B
    int sum = A + B;

    // If N is of the form
    // m*(A+B)+y
    if (N % sum <= A - 1)
        return "Bob";
    // Otherwise,
    else
        return "Alice";
}

// Driver code
int main()
{
    // Input
    int N = 3, A = 1, B = 2;
    // Function call
    cout << NimGame(N, A, B) << endl;

    return 0;
}
```

### Java

```java
// Java Program for the above approach
import java.io.*;

class GFG
{

  // Function to find the winner of the
  // game
  public static String NimGame(int N, int A, int B)
  {

    // Stores sum of A and B
    int sum = A + B;

    // If N is of the form
    // m*(A+B)+y
    if (N % sum <= A - 1)
      return "Bob";

    // Otherwise,
    else
      return "Alice";
  }

  public static void main (String[] args)
  {

    // Input
    int N = 3, A = 1, B = 2;

    // Function call
    System.out.println(NimGame(N, A, B));

  }
}

// This code is contributed by Potta Lokesh
```

### Python

```python
# Python3 program of the above approach

# Function to find the winner of the game
def NimGame(N, A, B):

    # Stores sum of A and B
    sum = A + B

    # If N is of the form
    # m*(A+B)+y
    if (N % sum <= A - 1):
        return "Bob"

    # Otherwise,
    else:
        return "Alice"

# Driver code

# Input
N = 3
A = 1
B = 2

# Function call
print(NimGame(N, A, B))

# This code is contributed by amreshkumar3
```

### C#

```csharp
// C# program of the above approach
using System;

class GFG{

// Function to find the winner of the
// game
public static String NimGame(int N, int A, int B)
{

    // Stores sum of A and B
    int sum = A + B;

    // If N is of the form
    // m*(A+B)+y
    if (N % sum <= A - 1)
        return "Bob";

    // Otherwise,
    else
        return "Alice";
}

// Driver code
static void Main()
{

    // Input
    int N = 3, A = 1, B = 2;

    // Function call
    Console.Write(NimGame(N, A, B));
}
}

// This code is contributed by SoumikMondal
```

### JavaScript

```javascript
<script>
        // JavaScript program for the above approach

        // Function to find the winner of the
        // game
        function NimGame(N, A, B) {
            // Stores sum of A and B
            let sum = A + B;

            // If N is of the form
            // m*(A+B)+y
            if (N % sum <= A - 1)
                return "Bob";
            // Otherwise,
            else
                return "Alice";
        }

        // Driver code

        // Input
        let N = 3, A = 1, B = 2;
        // Function call
        document.write(NimGame(N, A, B) + "<br>");

  // This code is contributed by Potta Lokesh
    </script>
```

**输出**

```
Bob
```

时间复杂度: `O(1)`
辅助空间: `O(1)`