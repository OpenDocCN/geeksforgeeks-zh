# 计算可以攻击 N * N 棋盘上给定棋子的骑士数量

> 原文：[https://www.geeksforgeeks.org/count-knights-that-can-attack-a-given-pawn-in-an-n-n-board/](https://www.geeksforgeeks.org/count-knights-that-can-attack-a-given-pawn-in-an-n-n-board/)

给定一个大小为 `N * 2` 的二维数组 `knights[][]`，表格中的每一行 `{ X, Y }` 代表骑士的坐标，一个数组 `pawn[]` 代表一个 `N * N` 棋盘中一个卒的坐标，任务是找出棋盘中正在攻击该卒的骑士数量。

## 示例

**输入：** `knights[][] = { { 0, 4 }, { 4, 5 }, { 1, 4 }, { 3, 1 } }`, `pawn[] = { 2, 3 }`
**输出：** `2`
**说明：**
坐标 `{ 0, 4 }` 和 `{ 3, 1 }` 处出现的骑士正在攻击棋子。
因此，要求的输出为 `2`。

**输入：** `knights[][] = { { 4, 6 }, { 7, 5 }, { 5, 5 } }`, `pawn[] = { 6, 7 }`
**输出：** `3`
**说明：**
坐标 `{ 4, 6 }`, `{ 7, 5 }` 和 `{ 5, 5 }` 处出现的骑士正在攻击棋子。
因此，要求的输出为 `3`。

## 方法

按照下面给出的步骤解决问题：

*   初始化一个变量，比如 `cntKnights`，来存储攻击棋子的骑士数量。
*   使用变量 `i` 遍历 `knights[][]` 数组，对于每个数组元素 `knights[i]`，检查数组 `{ (knights[i][0] - pawn[0]), (knights[i][1] - pawn[1]) }` 是否等于 `{ 1, 2 }` 或 `{ 2, 1 }`。如果发现为真，则将 `cntKnights` 的数值增加 `1`。
*   最后，打印 `cntKnights` 的值。

下面是上述方法的实现：

## C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to count the knights that are
// attacking the pawn in an M * M board
int cntKnightsAttackPawn(int knights[][2],
                         int pawn[], int M)
{
    // Stores count of knights that
    // are attacking the pawn
    int cntKnights = 0;

    // Traverse the knights[][] array
    for (int i = 0; i < M; i++) {

        // Stores absolute difference of X
        // co-ordinate of i-th knight and pawn
        int X = abs(knights[i][0]
                    - pawn[0]);

        // Stores absolute difference of Y
        // co-ordinate of i-th knight and pawn
        int Y = abs(knights[i][1]
                    - pawn[1]);

        // If X is 1 and Y is 2 or
        // X is 2 and Y is 1
        if ((X == 1 && Y == 2)
            || (X == 2 && Y == 1)) {

            // Update cntKnights
            cntKnights++;
        }
    }

    return cntKnights;
}

// Driver Code
int main()
{

    int knights[][2] = { { 0, 4 }, { 4, 5 },
                         { 1, 4 }, { 3, 1 } };

    int pawn[] = { 2, 3 };

    // Stores total count of knights
    int M = sizeof(knights)
            / sizeof(knights[0]);

    cout << cntKnightsAttackPawn(
        knights, pawn, M);

    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
import java.io.*;
import java.lang.Math;

class GFG{

// Function to count the knights that are
// attacking the pawn in an M * M board
static int cntKnightsAttackPawn(int knights[][],
                                int pawn[], int M)
{

    // Stores count of knights that
    // are attacking the pawn
    int cntKnights = 0;

     // Traverse the knights[][] array
    for(int i = 0; i < M; i++)
    {

        // Stores absolute difference of X
        // co-ordinate of i-th knight and pawn
        int X = Math.abs(knights[i][0] - pawn[0]);

        // Stores absolute difference of Y
        // co-ordinate of i-th knight and pawn
        int Y = Math.abs(knights[i][1] - pawn[1]);

        // If X is 1 and Y is 2 or
        // X is 2 and Y is 1
        if ((X == 1 && Y == 2) ||
            (X == 2 && Y == 1))
        {

            // Update cntKnights
            cntKnights++;
        }
    }
    return cntKnights;
}

// Driver code
public static void main(String[] args)
{
    int[][] knights = { { 0, 4 }, { 4, 5 },
                        { 1, 4 }, { 3, 1 } };

    int[] pawn = new int[]{2, 3};

    // Stores total count of knights
    int M = knights.length;

    System.out.println(cntKnightsAttackPawn(
        knights, pawn, M));
}
}

// This code is contributed by vandanakillari54935
```

## Python 3

```python
# Python program to implement
# the above approach

# Function to count the knights that are
# attacking the pawn in an M * M board
def cntKnightsAttackPawn(knights, pawn, M):

    # Stores count of knights that
    # are attacking the pawn
    cntKnights = 0;

    # Traverse the knights array
    for i in range(M):

        # Stores absolute difference of X
        # co-ordinate of i-th knight and pawn
        X = abs(knights[i][0] - pawn[0]);

        # Stores absolute difference of Y
        # co-ordinate of i-th knight and pawn
        Y = abs(knights[i][1] - pawn[1]);

        # If X is 1 and Y is 2 or
        # X is 2 and Y is 1
        if ((X == 1 and Y == 2) or (X == 2 and Y == 1)):

            # Update cntKnights
            cntKnights += 1;

    return cntKnights;

# Driver code
if __name__ == '__main__':
    knights = [[0, 4], [4, 5], [1, 4], [3, 1]];

    pawn = [2, 3];

    # Stores total count of knights
    M = len(knights);

    print(cntKnightsAttackPawn(knights, pawn, M));

# This code is contributed by Amit Katiyar
```

## C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG
{

  // Function to count the knights that are
  // attacking the pawn in an M * M board
  static int cntKnightsAttackPawn(int[,] knights, int[] pawn, int M)
  {
    // Stores count of knights that
    // are attacking the pawn
    int cntKnights = 0;

    // Traverse the knights[][] array
    for (int i = 0; i < M; i++) {

      // Stores absolute difference of X
      // co-ordinate of i-th knight and pawn
      int X = Math.Abs(knights[i, 0] - pawn[0]);

      // Stores absolute difference of Y
      // co-ordinate of i-th knight and pawn
      int Y = Math.Abs(knights[i, 1] - pawn[1]);

      // If X is 1 and Y is 2 or
      // X is 2 and Y is 1
      if ((X == 1 && Y == 2)
          || (X == 2 && Y == 1)) {

        // Update cntKnights
        cntKnights++;
      }
    }

    return cntKnights;
  }

  // Driver code
  static void Main()
  {
    int[,] knights = {{ 0, 4 }, { 4, 5 }, { 1, 4 }, { 3, 1 }};

    int[] pawn = {2, 3};

    // Stores total count of knights
    int M = knights.GetLength(0);

    Console.WriteLine(cntKnightsAttackPawn(knights, pawn, M));
  }
}

// This code is contributed by divyeshrabadiya07
```

## JavaScript

```javascript
<script>

// javascript program for the above approach

// Function to count the knights that are
// attacking the pawn in an M * M board
function cntKnightsAttackPawn(knights,
                                pawn, M)
{

    // Stores count of knights that
    // are attacking the pawn
    let cntKnights = 0;

     // Traverse the knights[][] array
    for(let i = 0; i < M; i++)
    {

        // Stores absolute difference of X
        // co-ordinate of i-th knight and pawn
        let X = Math.abs(knights[i][0] - pawn[0]);

        // Stores absolute difference of Y
        // co-ordinate of i-th knight and pawn
        let Y = Math.abs(knights[i][1] - pawn[1]);

        // If X is 1 and Y is 2 or
        // X is 2 and Y is 1
        if ((X == 1 && Y == 2) ||
            (X == 2 && Y == 1))
        {

            // Update cntKnights
            cntKnights++;
        }
    }
    return cntKnights;
}

// Driver Code

        let knights = [[ 0, 4 ], [ 4, 5 ],
                        [ 1, 4 ], [ 3, 1 ]];

    let pawn = [2, 3];

    // Stores total count of knights
    let M = knights.length;

    document.write(cntKnightsAttackPawn(
        knights, pawn, M));

</script>
```

**输出**

```
2
```

**时间复杂度：** `O(M)`，其中 `M` 为骑士总数。
**辅助空间：** `O(1)`。