# 计算给定周长下可能的直角三角形数量

> 原文: [https://www.geeksforgeeks.org/count-number-of-right-triangles-possible-with-a-given-perimeter/](https://www.geeksforgeeks.org/count-number-of-right-triangles-possible-with-a-given-perimeter/)

给定周长 `P`，任务是找出周长等于 `P` 的直角三角形的可能数量。

示例:

```
Input: P = 12
Output: number of right triangles = 1 
The only right angle possible is with sides 
hypotenuse = 5, perpendicular = 4 and base = 3.

Input: P = 840
Output: number of right triangles = 8
```

所以目标是找到满足方程 `a + b + c = P` 和 `a^2 + b^2 = c^2` 的解的数量。

一个**天真的**方法是对 `a`（1 到 `P/2`）和 `b`（`a+1` 到 `P/3`）运行两个循环，然后使 `c = P - a - b`，如果 `a*a + b*b == c*c` 计数增加 1。这需要 `O(P^2)` 时间。

一个**有效的**方法可以通过一些代数操作找到:

> `a^2 + b^2 = c^2` 或 `(a+b)^2 - 2ab = c^2` 或 `(P-c)^2 - 2ab = c^2` 或 `P^2 - 2cP - 2ab = 0` 或 `2ab = P^2 - 2cP` 或 `2ab = P^2 - 2P(P-a-b)` 或 `2a(P-b) = P(P-2b)` 或 `a = (P/2) * ((P-2b)/(P-b))`

由于 `a + c > b` 或 `P - b > b` 或 `b < P/2`。因此，将 `b` 从 1 迭代到 `P/2`，计算 `a` 并仅存储整数 `a` 将给出给定 `P` 的所有解。对于奇数 `P`，不可能有直角三角形，因为直角三角形遵循[勾股定理](https://www.geeksforgeeks.org/find-pythagorean-triplet-in-an-unsorted-array/)。使用配对列表存储 `a` 的值，并在最后返回计数。

以下是上述办法的实施情况。

## C++

```cpp
// C++ program to find the number of
// right triangles with given perimeter
#include<bits/stdc++.h>
using namespace std;

// Function to return the count
int countTriangles(int P)
{
  // making a list to store (a, b) pairs
  vector<pair<int,int>> store;

  // no triangle if P is odd
  if (P % 2 != 0)
    return 0;
  else
  {
    int count = 1;

    for(int b = 1; b < P / 2; b++)
    {
      float a = (float)P / 2.0f * ((float)((float)P -
                                           2.0 * (float)b) /
                                   ((float)P - (float)b));

      int inta = (int)(a);

      if (a == inta)
      {
        // make (a, b) pair in sorted order
        pair<int,int> ab;

        if(inta<b)
        {
          ab = {inta, b};
        }
        else
        {
          ab = {b, inta};
        }

        // check to avoid duplicates
        if(find(store.begin(), store.end(), ab) == store.end())
        {
          count += 1;

          // store the new pair
          store.push_back(ab);
        }
      }

    }
    return count;
  }
}

// Driver Code
int main()
{
  int P = 840;
  cout << "number of right triangles = " << countTriangles(P);
  return 0;
}

// This code is contributed by rutvik_56.
```

## Python 3

```python
# python program to find the number of
# right triangles with given perimeter

# Function to return the count
def countTriangles(P):

    # making a list to store (a, b) pairs
    store = []

    # no triangle if P is odd
    if P % 2 != 0:
        return 0
    else:
        count = 0
        for b in range(1, P // 2):

            a = P / 2 * ((P - 2 * b) / (P - b))
            inta = int(a)
            if (a == inta):

                # make (a, b) pair in sorted order
                ab = tuple(sorted((inta, b)))

                # check to avoid duplicates
                if ab not in store:
                    count += 1
                    # store the new pair
                    store.append(ab)
        return count

# Driver Code
P = 840
print("number of right triangles = " + str(countTriangles(P)))
```

**Output:**

```
number of right triangles = 8
```

**时间复杂度:** `O(P)`