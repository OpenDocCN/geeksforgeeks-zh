# 检查物品是否可以用秤和一些砝码测量

> 原文：[https://www.geeksforgeeks.org/check-if-item-can-be-measured-using-a-scale-and-some-weights/](https://www.geeksforgeeks.org/check-if-item-can-be-measured-using-a-scale-and-some-weights/)

给定质量的一些重量 `a^0`、`a^1`、`a^2`、…、`a^100`（`a` 为整数），以及可以在秤的两侧放置重量的秤。检查重量 `W` 的特定项目是否可以使用这些重量和秤进行测量。

## 约束

`2 ≤ W ≤ 10^9`

## 示例

**输入：** `a = 2`，`W = 5`
**输出：** YES
**说明：** 质量的重量 (`2^0 = 1`) 和 (`2^2 = 4`) 可以放在秤的一侧，物品可以放在另一侧，即 `1 + 4 = 5`

**输入：** `a = 4`，`W = 11`
**输出：** YES
**说明：** 重物 (`4^0 = 1`) 和 (`4^1 = 4`) 可将物品放在一侧，重物 (`4^2 = 16`) 可放在另一侧，即 `1 + 4 + 11 = 16`

**输入：** `a = 4`，`W = 7`
**输出：** NO

## 方法

*   首先，可以仔细观察，对于 `a = 2` 或 `a = 3`，答案总是存在的。
*   维护一个包含质量权重的数组，并且只包含小于 `10^9` 的权重。
*   现在，这个问题可以递归地解决，要么包含包含项的一侧的当前重量，要么包含包含该项的另一侧的当前重量，要么根本不使用该重量。

下面是上述方法的实现。

## C++

```cpp
// CPP Program to check whether an item
// can be measured using some weight and
// a weighing scale.
#include <bits/stdc++.h>
using namespace std;

// Variable to denote that answer has
// been found
int found = 0;

void solve(int idx, int itemWt, int wts[],
           int N)
{
    if (found)
        return;

    // Item has been measured
    if (itemWt == 0) {
        found = 1;
        return;
    }

    // If the index of current weight
    // is greater than totalWts
    if (idx > N)
        return;

    // Current weight is not included
    // on either side
    solve(idx + 1, itemWt, wts, N);

    // Current weight is included on the
    // side containing item
    solve(idx + 1, itemWt + wts[idx], wts,
          N);

    // Current weight is included on the
    // side opposite to the side
    // containing item
    solve(idx + 1, itemWt - wts[idx], wts,
          N);
}

// This function computes the required array
// of weights using a
bool checkItem(int a, int W)
{
    // If the a is 2 or 3, answer always
    // exists
    if (a == 2 || a == 3)
        return 1;

    int wts[100]; // weights array
    int totalWts = 0; // feasible weights
    wts[0] = 1;
    for (int i = 1;; i++) {
        wts[i] = wts[i - 1] * a;
        totalWts++;

        // if the current weight
        // becomes greater than 1e9
        // break from the loop
        if (wts[i] > 1e9)
            break;
    }
    solve(0, W, wts, totalWts);
    if (found)
        return 1;

    // Item can't be measured
    return 0;
}

// Driver Code to test above functions
int main()
{
    int a = 2, W = 5;
    if (checkItem(a, W))
        cout << "YES" << endl;
    else
        cout << "NO" << endl;

    a = 4, W = 11, found = 0;
    if (checkItem(a, W))
        cout << "YES" << endl;
    else
        cout << "NO" << endl;

    a = 4, W = 7, found = 0;
    if (checkItem(a, W))
        cout << "YES" << endl;
    else
        cout << "NO" << endl;
    return 0;
}
```

## Java

```java
// Java Program to check whether an item
// can be measured using some weight and
// a weighing scale.

class GFG {

    // Variable to denote that answer has
    // been found
    static int found = 0;

    static void solve(int idx, int itemWt, int wts[], int N) {
        if (found == 1) {
            return;
        }

        // Item has been measured
        if (itemWt == 0) {
            found = 1;
            return;
        }

        // If the index of current weight
        // is greater than totalWts
        if (idx > N) {
            return;
        }

        // Current weight is not included
        // on either side
        solve(idx + 1, itemWt, wts, N);

        // Current weight is included on the
        // side containing item
        solve(idx + 1, itemWt + wts[idx], wts,
                N);

        // Current weight is included on the
        // side opposite to the side
        // containing item
        solve(idx + 1, itemWt - wts[idx], wts,
                N);
    }

    // This function computes the required array
    // of weights using a
    static boolean checkItem(int a, int W) {
        // If the a is 2 or 3, answer always
        // exists
        if (a == 2 || a == 3) {
            return true;
        }

        int wts[] = new int[100]; // weights array
        int totalWts = 0; // feasible weights
        wts[0] = 1;
        for (int i = 1;; i++) {
            wts[i] = wts[i - 1] * a;
            totalWts++;

            // if the current weight
            // becomes greater than 1e9
            // break from the loop
            if (wts[i] > 1e9) {
                break;
            }
        }
        solve(0, W, wts, totalWts);
        if (found == 1) {
            return true;
        }

        // Item can't be measured
        return false;
    }

    // Driver Code to test above functions
    public static void main(String[] args) {

        int a = 2, W = 5;
        if (checkItem(a, W)) {
            System.out.println("YES");
        } else {
            System.out.println("NO");
        }

        a = 4; W = 11; found = 0;
        if (checkItem(a, W)) {
            System.out.println("YES");
        } else {
            System.out.println("NO");
        }

        a = 4; W = 7; found = 0;
        if (checkItem(a, W)) {
            System.out.println("YES");
        } else {
            System.out.println("NO");
        }
    }
}
```

## Python 3

```python
# Python3 Program to check whether an item
# can be measured using some weight and
# a weighing scale.

# Variable to denote that answer has been found
found = 0

def solve(idx, itemWt, wts, N):
    global found
    if found == 1:
        return

    # Item has been measured
    if itemWt == 0:
        found = 1
        return

    # If the index of current weight
    # is greater than totalWts
    if idx > N:
        return

    # Current weight is not included
    # on either side
    solve(idx + 1, itemWt, wts, N)

    # Current weight is included on the
    # side containing item
    solve(idx + 1, itemWt + wts[idx], wts, N)

    # Current weight is included on the
    # side opposite to the side
    # containing item
    solve(idx + 1, itemWt - wts[idx], wts, N)

# This function computes the required array
# of weights using a
def checkItem(a, W):
    global found
    # If the a is 2 or 3, answer always
    # exists
    if a == 2 or a == 3:
        return True

    wts = [0]*100 # weights array
    totalWts = 0 # feasible weights
    wts[0] = 1
    i = 1
    while True:
        wts[i] = wts[i - 1] * a
        totalWts+=1

        # if the current weight
        # becomes greater than 1e9
        # break from the loop
        if wts[i] > 1e9:
            break
        i+=1
    solve(0, W, wts, totalWts)
    if found == 1:
        return True

    # Item can't be measured
    return False

a, W = 2, 5
if checkItem(a, W):
    print("YES")
else:
    print("NO")

a, W, found = 4, 11, 0
if checkItem(a, W):
    print("YES")
else:
    print("NO")

a, W, found = 4, 7, 0
if checkItem(a, W):
    print("YES")
else:
    print("NO")
```

## C#

```csharp
// C# Program to check whether an item
// can be measured using some weight and
// a weighing scale.
using System;
public class GFG {
    // Variable to denote that answer has
    // been found
    static int found = 0;

    static void solve(int idx, int itemWt, int []wts, int N) {
        if (found == 1) {
            return;
        }

        // Item has been measured
        if (itemWt == 0) {
            found = 1;
            return;
        }

        // If the index of current weight
        // is greater than totalWts
        if (idx > N) {
            return;
        }

        // Current weight is not included
        // on either side
        solve(idx + 1, itemWt, wts, N);

        // Current weight is included on the
        // side containing item
        solve(idx + 1, itemWt + wts[idx], wts, N);

        // Current weight is included on the
        // side opposite to the side
        // containing item
        solve(idx + 1, itemWt - wts[idx], wts, N);
    }

    // This function computes the required array
    // of weights using a
    static bool checkItem(int a, int W) {
        // If the a is 2 or 3, answer always
        // exists
        if (a == 2 || a == 3) {
            return true;
        }

        int []wts = new int[100]; // weights array
        int totalWts = 0; // feasible weights
        wts[0] = 1;
        for (int i = 1;; i++) {
            wts[i] = wts[i - 1] * a;
            totalWts++;

            // if the current weight
            // becomes greater than 1e9
            // break from the loop
            if (wts[i] > 1e9) {
                break;
            }
        }
        solve(0, W, wts, totalWts);
        if (found == 1) {
            return true;
        }

        // Item can't be measured
        return false;
    }

    // Driver Code to test above functions
    public static void Main() {
        int a = 2, W = 5;
        if (checkItem(a, W)) {
            Console.WriteLine("YES");
        } else {
            Console.WriteLine("NO");
        }

        a = 4; W = 11; found = 0;
        if (checkItem(a, W)) {
            Console.WriteLine("YES");
        } else {
            Console.WriteLine("NO");
        }

        a = 4; W = 7; found = 0;
        if (checkItem(a, W)) {
            Console.WriteLine("YES");
        } else {
            Console.WriteLine("NO");
        }
    }
}
//this code contributed by Rajput-Ji
```

## java 描述语言

```javascript
// Javascript Program to check whether an item
// can be measured using some weight and
// a weighing scale.

// Variable to denote that answer has
// been found
let found = 0;

function solve(idx, itemWt, wts, N) {
    if (found)
        return;

    // Item has been measured
    if (itemWt == 0) {
        found = 1;
        return;
    }

    // If the index of current weight
    // is greater than totalWts
    if (idx > N)
        return;

    // Current weight is not included
    // on either side
    solve(idx + 1, itemWt, wts, N);

    // Current weight is included on the
    // side containing item
    solve(idx + 1, itemWt + wts[idx], wts, N);

    // Current weight is included on the
    // side opposite to the side
    // containing item
    solve(idx + 1, itemWt - wts[idx], wts, N);
}

// This function computes the required array
// of weights using a
function checkItem(a, W) {
    // If the a is 2 or 3, answer always
    // exists
    if (a == 2 || a == 3)
        return 1;

    let wts = new Array(100); // weights array
    let totalWts = 0; // feasible weights
    wts[0] = 1;
    for (let i = 1;; i++) {
        wts[i] = wts[i - 1] * a;
        totalWts++;

        // if the current weight
        // becomes greater than 1e9
        // break from the loop
        if (wts[i] > 1e9)
            break;
    }
    solve(0, W, wts, totalWts);
    if (found)
        return 1;

    // Item can't be measured
    return 0;
}

let a = 2, W = 5;
if (checkItem(a, W))
    document.write("YES" + "</br>");
else
    document.write("NO" + "</br>");

a = 4, W = 11, found = 0;
if (checkItem(a, W))
    document.write("YES" + "</br>");
else
    document.write("NO" + "</br>");

a = 4, W = 7, found = 0;
if (checkItem(a, W))
    document.write("YES" + "</br>");
else
    document.write("NO" + "</br>");

// This code is contributed by decode2207.
```

**Output:**

```
YES
YES
NO
```

**时间复杂度:** O(3^N)，其中 N 不能超过 20，因为 4^20 大于 10^9。