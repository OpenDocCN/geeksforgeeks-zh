# 要翻转的最小单元，以获得具有相等元素的 2*2 子矩阵

> 原文:[https://www . geeksforgeeks . org/要翻转以获得 22 个元素相等的子矩阵的最小单元数/](https://www.geeksforgeeks.org/minimum-cells-to-be-flipped-to-get-a-22-submatrix-with-equal-elements/)

给定一个大小为 **M * N** 的矩阵，任务是找到必须翻转的最小单元数的计数，以便至少有一个大小为 2*2 的子矩阵具有所有相等的元素。
**例:**

> ·t0±input:

**方法:**对于每个大小为 2*2 的子矩阵，计算其中 0 和 1 的数量，这两者的最小值将是获得所有元素相等的矩阵所需的翻转次数。所有子矩阵的最小值就是所需答案。
以下是上述办法的实施情况:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the minimum flips
// required such that the submatrix from
// mat[i][j] to mat[i + 1][j + 1]
// contains all equal elements
int minFlipsSub(string mat[], int i, int j)
{
    int cnt0 = 0, cnt1 = 0;

    if (mat[i][j] == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i][j + 1] == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i + 1][j] == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i + 1][j + 1] == '1')
        cnt1++ ;
    else
        cnt0++ ;

    return min(cnt0, cnt1);
}

// Function to return the minimum number
// of slips required such that the matrix
// contains at least a single submatrix
// of size 2*2 with all equal elements
int minFlips(string mat[], int r, int c)
{

    // To store the result
    int res = INT_MAX;

    // For every submatrix of size 2*2
    for (int i = 0; i < r - 1; i++) {
        for (int j = 0; j < c - 1; j++) {

            // Update the count of flips required
            // for the current submatrix
            res = min(res, minFlipsSub(mat, i, j));
        }
    }

    return res;
}

// Driver code
int main()
{
    string mat[] = { "0101", "0101", "0101" };
    int r = sizeof(mat) / sizeof(string);
    int c = mat[0].length();

    cout << minFlips(mat, r, c);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java implementation of the approach
class GFG
{

// Function to return the minimum flips
// required such that the submatrix from
// mat[i][j] to mat[i + 1][j + 1]
// contains all equal elements
static int minFlipsSub(String mat[], int i, int j)
{
    int cnt0 = 0, cnt1 = 0;

    if (mat[i].charAt(j) == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i].charAt(j+1) == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i + 1].charAt(j) == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i + 1].charAt(j+1) == '1')
        cnt1++ ;
    else
        cnt0++ ;

    return Math.min(cnt0, cnt1);
}

// Function to return the minimum number
// of slips required such that the matrix
// contains at least a single submatrix
// of size 2*2 with all equal elements
static int minFlips(String mat[], int r, int c)
{
    // To store the result
    int res = Integer.MAX_VALUE;

    // For every submatrix of size 2*2
    for (int i = 0; i < r - 1; i++)
    {
        for (int j = 0; j < c - 1; j++)
        {
            // Update the count of flips required
            // for the current submatrix
            res = Math.min(res, minFlipsSub(mat, i, j));
        }
    }
    return res;
}

// Driver code
public static void main(String[] args)
{
    String mat[] = { "0101", "0101", "0101" };
    int r = mat.length;
    int c = mat[0].length();

    System.out.print(minFlips(mat, r, c));
}
}

// This code is contributed by 29AjayKumar
```

## 蟒蛇 3

```cpp
# Python 3 implementation of the approach
import sys

# Function to return the minimum flips
# required such that the submatrix from
# mat[i][j] to mat[i + 1][j + 1]
# contains all equal elements
def minFlipsSub(mat, i, j):
    cnt0 = 0
    cnt1 = 0

    if (mat[i][j] == '1'):
        cnt1 += 1
    else:
        cnt0 += 1

    if (mat[i][j + 1] == '1'):
        cnt1 += 1
    else:
        cnt0 += 1

    if (mat[i + 1][j] == '1'):
        cnt1 += 1
    else:
        cnt0 += 1

    if (mat[i + 1][j + 1] == '1'):
        cnt1 += 1
    else:
        cnt0 += 1

    return min(cnt0, cnt1)

# Function to return the minimum number
# of slips required such that the matrix
# contains at least a single submatrix
# of size 2*2 with all equal elements
def minFlips(mat, r, c):

    # To store the result
    res = sys.maxsize

    # For every submatrix of size 2*2
    for i in range(r - 1):
        for j in range(c - 1):

            # Update the count of flips required
            # for the current submatrix
            res = min(res, minFlipsSub(mat, i, j))

    return res

# Driver code
if __name__ == '__main__':
    mat = ["0101", "0101", "0101"]
    r = len(mat)
    c = len(mat[0])

    print(minFlips(mat, r, c))

# This code is contributed by Surendra_Gangwar
```

## C#

```cpp
// C# implementation of the approach
using System;

class GFG
{

// Function to return the minimum flips
// required such that the submatrix from
// mat[i,j] to mat[i + 1,j + 1]
// contains all equal elements
static int minFlipsSub(String []mat,
                       int i, int j)
{
    int cnt0 = 0, cnt1 = 0;

    if (mat[i][j] == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i][j + 1] == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i + 1][j] == '1')
        cnt1++ ;
    else
        cnt0++ ;

    if (mat[i + 1][j + 1] == '1')
        cnt1++ ;
    else
        cnt0++ ;

    return Math.Min(cnt0, cnt1);
}

// Function to return the minimum number
// of slips required such that the matrix
// contains at least a single submatrix
// of size 2*2 with all equal elements
static int minFlips(String []mat,
                    int r, int c)
{
    // To store the result
    int res = int.MaxValue;

    // For every submatrix of size 2*2
    for (int i = 0; i < r - 1; i++)
    {
        for (int j = 0; j < c - 1; j++)
        {
            // Update the count of flips required
            // for the current submatrix
            res = Math.Min(res, minFlipsSub(mat, i, j));
        }
    }
    return res;
}

// Driver code
public static void Main(String[] args)
{
    String []mat = { "0101", "0101", "0101" };
    int r = mat.Length;
    int c = mat.GetLength(0);

    Console.Write(minFlips(mat, r, c));
}
}

// This code is contributed by 29AjayKumar
```

## java 描述语言

```cpp
<script>
// javascript implementation of the approach   
// Function to return the minimum flips
    // required such that the submatrix from
    // mat[i][j] to mat[i + 1][j + 1]
    // contains all equal elements
    function minFlipsSub( mat , i , j)
    {
        var cnt0 = 0, cnt1 = 0;

        if (mat[i].charAt(j) == '1')
            cnt1++ ;
        else
            cnt0++ ;

        if (mat[i].charAt(j + 1) == '1')
            cnt1++ ;
        else
            cnt0++ ;

        if (mat[i + 1].charAt(j) == '1')
            cnt1++ ;
        else
            cnt0++ ;

        if (mat[i + 1].charAt(j + 1) == '1')
            cnt1++ ;
        else
            cnt0++ ;

        return Math.min(cnt0, cnt1);
    }

    // Function to return the minimum number
    // of slips required such that the matrix
    // contains at least a single submatrix
    // of size 2*2 with all equal elements
    function minFlips(mat , r , c)
    {

        // To store the result
        var res = Number.MAX_VALUE;

        // For every submatrix of size 2*2
        for (i = 0; i < r - 1; i++)
        {
            for (j = 0; j < c - 1; j++)
            {

                // Update the count of flips required
                // for the current submatrix
                res = Math.min(res, minFlipsSub(mat, i, j));
            }
        }
        return res;
    }

    // Driver code
        var mat = [ "0101", "0101", "0101" ];
        var r = mat.length;
        var c = mat[0].length;

        document.write(minFlips(mat, r, c));

// This code is contributed by Rajput-Ji
</script>
```

**Output:** 

```cpp
2
```