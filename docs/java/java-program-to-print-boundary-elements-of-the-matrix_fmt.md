# 打印矩阵边界元素的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-print-boundary-elements-of-the-matrix/](https://www.geeksforgeeks.org/java-program-to-print-boundary-elements-of-the-matrix/)

给定一个大小为 `行×列` 的矩阵，打印矩阵的边界元素。边界元素是那些在所有四个方向上都没有被元素包围的元素，即第一行、第一列、最后一行和最后一列中的元素。

例:

```java
Input :
         1 2 3
         4 5 6
         7 8 9
Output:  
        1 2 3
        4   6
        7 8 9
```

方式:

1.  将矩阵作为 `N × M` 维的用户输入。
2.  使用 `for` 循环打印矩阵的边界元素。

下面是问题陈述的实现:

## Java 实现

```java
// Java Program to Print Boundary
// Elements of the Matrix

import java.util.*;

public class GFG {

public void Boundary_Elements(int mat[][])
    {
        // Printing Input Matrix;
        System.out.println("Input Matrix is : ");

for (int i = 0; i < mat.length; i++) {
            for (int j = 0; j < mat[i].length; j++) {

System.out.print(mat[i][j]);
            }

System.out.println();
        }

// Printing Boundary Values of Matrix
        System.out.println("Resultant Matrix is :");

for (int i = 0; i < mat.length; i++) {
            for (int j = 0; j < mat[i].length; j++) {

if (i == 0 || j == 0 || i == mat.length - 1
                    || j == mat[i].length - 1) {
                    System.out.print(mat[i][j]);
                }
                else {
                    // Printing Space if element
                    // is not at Boundary
                    System.out.print(" ");
                }
            }

System.out.println();
        }
    }
    public static void main(String[] args)
    {
        // Input Matrix
        int mat[][] = new int[][] { { 1, 2, 3 },
                                    { 4, 5, 6 },
                                    { 7, 8, 9 } };

GFG B_Values = new GFG();

B_Values.Boundary_Elements(mat);
    }
}
```

输出

```java
Input Matrix is :

Resultant Matrix is :

4 6

```

时间复杂度: `O(N × M)`，其中 `N` 和 `M` 是矩阵的维数。

空间复杂度: `O(N × M)`。