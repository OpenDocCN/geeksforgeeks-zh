# 十进制到十六进制转换的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-十进制到十六进制转换程序/](https://www.geeksforgeeks.org/java-program-for-decimal-to-hexadecimal-conversion/)

给定十进制数 `N`，将 `N` 转换为等效的十六进制数，即将基数为 10 的数转换为基数为 16 的数。十进制数字系统使用 10 位数字 0-9，十六进制数字系统使用 0-9，A-F 来表示任何数值。

## 例:

```java
Input : 10
Output: A

Input : 2545
Output: 9F1
```

## 逼近:

1.  将数字除以 16 并存储余数。
2.  现在将数字除以 16。
3.  重复以上两个步骤，直到数字不等于 0。
4.  现在以相反的顺序打印数组。

## 实施:

## 示例

### Java

```java
// Java program to convert Decimal Number
// to Hexadecimal Number

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

// Method 1
    // To convert decimal to hexadecimal
    static void decTohex(int n)
    {
        // Creating an array to store octal number
        int[] hexNum = new int[100];

// counter for hexadecimal number array
        int i = 0;
        while (n != 0) {

// Storing remainder in hexadecimal array
            hexNum[i] = n % 16;
            n = n / 16;
            i++;
        }

// Printing hexadecimal number array
        // in the reverse order
        for (int j = i - 1; j >= 0; j--) {
            if (hexNum[j] > 9)
                System.out.print((char)(55 + hexNum[j]));
            else
                System.out.print(hexNum[j]);
        }
    }

// Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input decimal number
        // to be converted into hexadecimal number
        int n = 2545;

// Calling the above Method1 over number 'n'
        // to convert this decimal into hexadecimal number
        decTohex(n);
    }
}
```

## 输出

```java
9F1
```

## 时间复杂度: O(对数 `N`)