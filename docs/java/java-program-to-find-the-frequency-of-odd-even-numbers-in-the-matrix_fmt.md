# 寻找矩阵中奇数与偶数频率的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-find-the-frequency-of-odd-even-numbers-in-the-matrix/](https://www.geeksforgeeks.org/java-program-to-find-the-frequency-of-odd-even-numbers-in-the-matrix/)

[矩阵](https://www.geeksforgeeks.org/matrix/)只是一个二维数组。就像在一维遍历操作中需要弄清楚一样。任务是找出给定矩阵中奇数和偶数的频率。

> 矩阵的大小定义为列数和行数的乘积。所以，矩阵的大小是 `m × n`。

在矩阵中：
*   `M` = 矩阵中的行数
*   `N` = 列数

**示例：**

```java
Input : M = 3
    N = 5
Output: Odd Number Frequency  = 9
    Even Number Frequency = 6

Input : M = 3
    N = 3
    {{1, 2, 5},
     {6, 7, 9},
     {3, 2, 1}}
Output: Odd Number Frequency  = 6
    Even Number Frequency = 3
```

## 接近

*   将两个计数器初始化为 `even = 0` 和 `odd = 0`。
*   遍历矩阵中的每个元素，检查 `(element % 2 == 0)`。
*   如果是，则递增 `even++`。
*   否则递增 `odd++`。

下面是该方法在 Java 中的实现。

## Java 实现

```java
// Importing Classes/Files
import java.io.*;

class GFG {

    // Function to compute frequency of odd/even numbers
    public static void findFreq(int[][] arr, int m, int n)
    {
        // Initializing the counter variables
        int even = 0, odd = 0;

        // Nested loops
        // Traversing through each element in the matrix
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                // Checking if the element is divisible by 2
                if (arr[i][j] % 2 == 0) {
                    // Increment even counter
                    even++;
                }
                else {
                    // Increment odd counter
                    odd++;
                }
            }
        }

        // Printing Counts of Even and odd numbers in matrix
        System.out.println("Odd Number Frequency: " + odd);
        System.out.println("Even Number Frequence: " + even);
    }

    // Main Driver Method
    public static void main(String[] args)
    {
        // Providing inputs to the matrix
        int m = 3, n = 5;
        // Here, m = Number of rows,
        // n = Number of columns

        // Entering elements in the matrix
        int[][] arr = { { 3, 4, 5, 6, 3 },
                        { 4, 3, 2, 7, 9 },
                        { 1, 5, 7, 2, 4 } };

        // Calling function to count frequency by
        // passing inputs to the function findFreq
        findFreq(arr, m, n);
    }
}
```

**输出**

```java
Odd Number Frequency: 9
Even Number Frequence: 6
```

**【时间复杂度】**：当遍历一维数组时，它取决于操作执行的数组的大小，因为其余操作要么是相同的顺序，要么是占用内存（变量）中的一些恒定空间。这里的遍历覆盖了该行的所有元素以及矩阵中的每一行。所以这取决于行和列的乘积。因此，时间复杂度是 `O(m * n)`。

**【空间复杂度】**：只是给变量分配内存，随后用变量的范围释放。因为没有为要执行的操作创建其他辅助空间。因此，所需的空间是恒定的，随后释放。默认分配 1，因此空间复杂度为 `O(1)`。

```java
Time Complexity  = O(Rows*Columns) or O(m * n)
Space Complexity = O(1)
```