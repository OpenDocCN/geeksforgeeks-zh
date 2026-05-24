# 对矩阵行进行排序的程序

> 原文：[https://www.geeksforgeeks.org/c-program-to-sort-rows-of-the-matrix/](https://www.geeksforgeeks.org/c-program-to-sort-rows-of-the-matrix/)

给定维度为 `N * M` 的矩阵 `arr[][]`，任务是对矩阵进行排序，使得每行都被排序，并且每行的第一个元素大于或等于前一行的最后一个元素。

**示例：**

> **输入：** `N = 3`，`M = 3`，`arr[][] = {{7, 8, 9}, {5, 6, 4}, {3, 1, 2}}`
> **输出：**
> 1 2 3
> 4 5 6
> 7 8 9

**方法：** 按照以下步骤解决问题：

1.  `遍历矩阵`
2.  对于每个矩阵元素，将其视为矩阵中的`最小元素`。检查在剩余的`矩阵`中是否存在较小的元素。
3.  如果发现为真，则交换当前元素和矩阵中的`最小元素`。
4.  最后打印`排序矩阵`。

下面是上述方法的实现：

## C语言实现

```cpp
// C program for the above approach
#include <stdio.h>
#include <stdlib.h>

#define SIZE 100

// Function to sort a matrix
void sort_matrix(int arr[SIZE][SIZE],
                 int N, int M)
{
    // Traverse over the matrix
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < M; j++) {
            // Current minimum element
            int minimum = arr[i][j];
            // Index of the current
            // minimum element
            int z = i;
            int q = j;
            // Check if any smaller element
            // is present in the matrix
            int w = j;
            for (int k = i; k < N; k++) {
                for (; w < M; w++) {
                    // Update the minimum element
                    if (arr[k][w] < minimum) {
                        minimum = arr[k][w];
                        // Update the index of
                        // the minimum element
                        z = k;
                        q = w;
                    }
                }
                w = 0;
            }
            // Swap the current element
            // and the minimum element
            int temp = arr[i][j];
            arr[i][j] = arr[z][q];
            arr[z][q] = temp;
        }
    }
}

// Function to print the sorted matrix
void printMat(int arr[SIZE][SIZE],
              int N, int M)
{
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < M; j++) {
            printf("%d ", arr[i][j]);
        }
        printf("\n");
    }
}

// Driver Code
int main()
{
    int N = 3, M = 3;
    int arr[SIZE][SIZE]
        = { { 7, 8, 9 },
            { 5, 6, 4 },
            { 3, 1, 2 } };
    // Sort the matrix
    sort_matrix(arr, N, M);
    // Print the sorted matrix
    printMat(arr, N, M);
    return 0;
}
```

**输出：**

```cpp
1 2 3
4 5 6
7 8 9
```

**时间复杂度：** O(N^4)
**辅助空间：** O(1)