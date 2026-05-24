# Java 程序打印直角三角形星形图案

> 原文：`https://www.geeksforgeks.org/java-program-to-print-right-triangle-star-pattern/`

在这篇文章中，我们将学习打印直角三角形星形图案。

**例：**

```java
Input : n = 5
Output: 
* 
* * 
* * * 
* * * * 
* * * * *  
```

**直角三角形星形图案：**

## Java

```java
import java.io.*;

// Java code to demonstrate right star triangle
public class GeeksForGeeks {
    // Function to demonstrate printing pattern
    public static void StarRightTriangle(int n)
    {
        int a, b;

        // outer loop to handle number of rows
        // k in this case
        for (a = 0; a < n; a++) {

            // inner loop to handle number of columns
            // values changing acc. to outer loop
            for (b = 0; b <= a; b++) {
                // printing stars
                System.out.print("* ");
            }

            // end-line
            System.out.println();
        }
    }

    // Driver Function
    public static void main(String args[])
    {
        int k = 5;
        StarRightTriangle(k);
    }
}
```

**输出**

```java
* 
* * 
* * * 
* * * * 
* * * * * 
```