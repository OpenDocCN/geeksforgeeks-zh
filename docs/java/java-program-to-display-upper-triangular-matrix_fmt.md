# 显示上三角矩阵的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-display-upper-triangular-matrix/](https://www.geeksforgeeks.org/java-program-to-display-upper-triangular-matrix/)

上三角矩阵是主矩阵下所有元素都为 0 的矩阵。一个必要条件是矩阵本质上必须是方阵。如果矩阵不是正方形矩阵，就永远不能称为上三角矩阵。

### 例子

```java
Input 1: mat[][] = { {2, 1, 4},
                     {1, 2, 3},  
                     {3, 6, 2} }

Output :  mat[][]= { {2, 1, 4},
                     {0, 2, 3},  
                     {0, 0, 2} }

Explaination: All the element below the principal diagonal needs to be 0.

Input 2 :   mat[][]=  { {4,7},
                        {2,8} }

Output :   mat[][]=   { {4,7},
                        {0,8} }

Input 3 :  mat[][]=  { {2,1,4,6},
                       {1,2,3,7},  
                       {3,6,2,8} }  
Output :   Matrix should be a Square Matrix
```

**方法:**

*   如果矩阵的行数和列数相等，则继续程序；否则，退出程序。
*   在整个矩阵上运行一个循环，对于行号大于列号的位置，将该位置的元素设为 0。

下面是上述方法的实现：

## Java

```java
// Java program to display upper triangular matrix

class GFG {

    // Function to print upper triangular matrix
    static void printUpperTriangular(int[][] mat, int n)
    {
        System.out.println("Upper Triangular Matrix is given by :-");
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (j >= i) {
                    System.out.print(mat[i][j] + " ");
                }
                else {
                    System.out.print(0 + " ");
                }
            }
            System.out.println();
        }
    }

    // Driver code
    public static void main(String[] args)
    {
        int[][] mat = { { 2, 1, 4 },
                        { 1, 2, 3 },
                        { 3, 6, 2 } };
        int n = mat.length;

        // Function call
        printUpperTriangular(mat, n);
    }
}
```

**输出**

```
Upper Triangular Matrix is given by :-
2 1 4 
0 2 3 
0 0 2 
```