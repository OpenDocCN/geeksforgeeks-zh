# 求矩阵的均值向量

> 原文：`https://www.geeksforgeeks.org/find-mean-vector-matrix/`

给定一个 `M×N` 大小的矩阵，任务是找到给定矩阵的**均值向量**。

**例：**

```
Input : mat[][] = {{1, 2, 3},
                   {4, 5, 6},
                   {7, 8, 9}}       
Output : Mean Vector is [4 5 6]
Mean of column 1 is (1 + 4 + 7) / 3 = 4
Mean of column 2 is (2 + 5 + 8) / 3 = 5
Mean of column 3 is (3 + 6 + 9) / 3 = 6

Input : mat[][] =  {{2, 4},
                    {6, 8}}
Output : Mean Vector is [4 6]
Mean of column 1 is (2 + 6) / 2 = 4
Mean of column 2 is (4 + 8) / 2 = 6
```

## 方法

我们取一个矩阵 `mat` 的尺寸 `5×3` 代表 5 个物体的长度、宽度和高度。现在，得到的**均值向量**将是以下格式的[行向量](https://en.wikipedia.org/wiki/Row_and_column_vectors)：

```
[mean(length) mean(breadth)  mean(height)]
```

**注意：** 如果我们有一个维度为 `M x N` 的矩阵，那么得到的[行向量](https://en.wikipedia.org/wiki/Row_and_column_vectors)的维度将是 `1 x N`。现在，只需[计算矩阵每一列的均值](https://en.wikipedia.org/wiki/Mean)，即可得到所需的均值向量。

## C++

```cpp
// C++ program to find mean vector
// of given matrix
#include <bits/stdc++.h>
using namespace std;
#define rows 3
#define cols 3

// Function to find mean vector
void meanVector(int mat[rows][cols])
{
    cout << "[ ";

    // loop to traverse each column
    for (int i = 0; i < rows; i++) {

        // to calculate mean of each row
        double mean = 0.00;

        // to store sum of elements of a column
        int sum = 0;

        for (int j = 0; j < cols; j++)
            sum += mat[j][i];

        mean = sum / rows;
        cout << mean << " ";
    }

    cout << "]";
}

// Drivers code
int main()
{

    int mat[rows][cols] = { { 1, 2, 3 },
                            { 4, 5, 6 },
                            { 7, 8, 9 } };

    meanVector(mat);

    return 0;
}
```

## Java

```java
// Java program to find
// mean vector of given matrix
import java.io.*;

class GFG
{
static int rows = 3;
static int cols = 3;

// Function to
// find mean vector
static void meanVector(int mat[][])
{
    System.out.print("[ ");

    // loop to traverse
    // each column
    for (int i = 0; i < rows; i++)
    {

        // to calculate mean
        // of each row
        double mean = 0.00;

        // to store sum of
        // elements of a column
        int sum = 0;

        for (int j = 0; j < cols; j++)
            sum += mat[j][i];

        mean = sum / rows;
        System.out.print((int)mean + " ");
    }

    System.out.print("]");
}

// Driver code
public static void main (String[] args)
{
    int mat[][] = {{1, 2, 3},
                   {4, 5, 6},
                   {7, 8, 9}};

    meanVector(mat);
}
}

// This code is contributed
// by anuj_67.
```

## Python3

```python
# Python3 program to find
# mean vector of given
# matrix
rows = 3;
cols = 3;

# Function to
# find mean vector
def meanVector(mat):
    print("[ ", end = "");

    # loop to traverse
    # each column
    for i in range(rows):

        # to calculate
        # mean of each row
        mean = 0.00;

        # to store sum of
        # elements of a column
        sum = 0;

        for j in range(cols):
            sum = sum + mat[j][i];

        mean = int(sum /rows);
        print(mean, end = " ");

    print("]");

# Driver Code
mat = [[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]];

meanVector(mat);

# This code is contributed
# by mits
```

## C#

```csharp
// C# program to find
// mean vector of given matrix
using System;

class GFG
{
static int rows = 3;
static int cols = 3;

// Function to
// find mean vector
static void meanVector(int [,]mat)
{
    Console.Write("[ ");

    // loop to traverse
    // each column
    for (int i = 0; i < rows; i++)
    {

        // to calculate mean
        // of each row
        double mean = 0.00;

        // to store sum of
        // elements of a column
        int sum = 0;

        for (int j = 0; j < cols; j++)
            sum += mat[j, i];

        mean = sum / rows;
        Console.Write((int)mean + " ");
    }

    Console.Write("]");
}

// Driver code
public static void Main ()
{
    int[,] mat = {{1, 2, 3},
                  {4, 5, 6},
                  {7, 8, 9}};

    meanVector(mat);
}
}

// This code is contributed
// by anuj_67.
```

## PHP

```php
<?php
// PHP program to find mean
// vector of given matrix
$rows = 3;
$cols = 3;

// Function to find mean vector
function meanVector($mat)
{
    global $rows ,$cols;
    echo "[ ";

    // loop to traverse
    // each column
    for ($i = 0; $i < $rows; $i++)
    {

        // to calculate
        // mean of each row
        $mean = 0.00;

        // to store sum of
        // elements of a column
        $sum = 0;

        for ($j = 0; $j < $cols; $j++)
            $sum += $mat[$j][$i];

        $mean = $sum /$rows;
        echo $mean , " ";
    }

    echo "]";
}

// Driver Code
$mat = array(array(1, 2, 3),
             array(4, 5, 6),
             array(7, 8, 9));

meanVector($mat);

// This code is contributed
// by anuj_6
?>
```

## JavaScript

```javascript
<script>

// Javascript program to find
// mean vector of given matrix
var rows = 3;
var cols = 3;

// Function to find mean vector
function meanVector(mat)
{
    document.write("[ ");

    // Loop to traverse
    // each column
    for (var i = 0; i < rows; i++)
    {

        // To calculate mean
        // of each row
        var mean = 0.00;

        // to store sum of
        // elements of a column
        var sum = 0;

        for (var j = 0; j < cols; j++)
            sum += mat[j][i];

        mean = sum / rows;
        document.write(mean + " ");
    }

    document.write("]");
}

// Driver code
var mat = [ [ 1, 2, 3 ],
            [ 4, 5, 6 ],
            [ 7, 8, 9 ] ];

meanVector(mat);

// This code is contributed by Kirti

</script>
```

**输出：**

```
[ 4 5 6 ]
```

**时间复杂度：** `O(rows * cols)`