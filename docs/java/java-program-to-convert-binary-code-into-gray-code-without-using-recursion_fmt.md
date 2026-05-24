# 不使用递归将二进制代码转换为格雷码的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-binary-code-to-gray-code-无需使用递归/](https://www.geeksforgeeks.org/java-program-to-convert-binary-code-into-gray-code-without-using-recursion/)

`二进制`一个数的代码是二进制(基数-2)数系中一个数的表示。在二进制数字系统中，每个数字只用两个字面值(0 和 1)表示。这些文字中的每一个都被称为一个`位`。二进制数字系统在数字电子电路中非常有用。

`灰色`数字的代码是使用二进制文字表示的数字。但是二进制码和格雷码的区别在于，在格雷码中，每对连续的数字只相差一位。格雷码对于实现 K-map 和纠错非常有用。

## 例:

```java
Binary -> 0100
Gray   -> 0110

Binary -> 0101
Gray   -> 0111
```

格雷码可以转换成二进制码，反之亦然。

## 二进制到灰度转换:

一个二进制码可以转换成它的等价格雷码，如:

*   二进制码的`MSB (most significant bit)`将是等价格雷码的`MSB`。
*   所有剩余的位是通过对二进制字符串中当前位置的位和前一个位置的位执行`XOR operation`获得的。

```java
Example:
Binary ->  0011010101
           0 XOR 0 XOR 1 XOR 1 XOR 0 XOR 1 XOR 0 XOR 1 XOR 0 XOR 1
           ↓  ↓     ↓     ↓     ↓     ↓     ↓     ↓     ↓     ↓
Gray   ->  0  0     1     0     1     1     1     1     1     1

Binary ->  0100110
Gray   ->  0110101
```

## 代码 1:

我们使用`^`通过使用`Integer.parseInt()`函数将字符串转换为整数值，然后对它们执行 Xor 运算来执行 xor 运算。

```java
// Java program to demonstrate Binary
// to Gray conversion

import java.io.*;

class GFG {

// converts the given binary string into its equivalent
    // gray code
    public static void toGray(String binary)
    {
        // a String variable to store the obtained gray
        // string.
        // the MSB of the gray code is the same as
        // the MSB of the binary string, i.e., binary[0]
        String gray = new String();

        gray += binary.charAt(0);

        for (int i = 1; i < binary.length(); i++)
        {
            // perform XOR on the previous bit and the
            // current bit of the binary string
            gray += (Integer.parseInt(String.valueOf(binary.charAt(i - 1))) ^
                     Integer.parseInt(String.valueOf(binary.charAt(i))));

        }

        System.out.println("The gray code of " + binary
                           + " is : " + gray);
    }

    public static void main(String[] args)
    {
        // a String variable to store the given binary
        // string
        String binary = "0011010101";

        toGray(binary);
    }
}
```

## 输出

```java
The gray code of 0011010101 is : 0010111111
```

## 代码 2:

我们做了一个单独的`用户定义的`函数，名为`xOR(char a, char b)`，它返回给我们两个数字 a 和 b 的 Xor。

```java
// Java program to demonstrate Binary
// to Gray conversion

import java.io.*;

class GFG {

    // an auxiliary method to perform XOR on two given
    // literals
    public static int xOR(char a, char b)
    {
        // return 1 if both bits are not same
        if (a != b)
            return 1;

        // else return 0
        return 0;
    }

    // converts the given binary string into its equivalent
    // gray code
    public static void toGray(String binary)
    {

        String gray = new String();

        gray += binary.charAt(0);

        // for all the other bits, traverse through the
        // binary string
        for (int i = 1; i < binary.length(); i++)
        {
            // calling xOR() method on the previous bit and
            // the current bit of the binary string
            gray += xOR(binary.charAt(i - 1),
                        binary.charAt(i));
        }

        System.out.println("The gray code of " + binary
                           + " is : " + gray);
    }

    // Driver method
    public static void main(String[] args)
    {
        // a String variable to store the given binary
        // string
        String binary = "0011010101";

        toGray(binary);

    }
}
```

## 输出

```java
The gray code of 0011010101 is : 0010111111
```