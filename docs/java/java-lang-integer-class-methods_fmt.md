# Java.lang.Integer 类及其方法

> 原文: [https://www.geeksforgeeks.org/java-lang-integer-class-methods/](https://www.geeksforgeeks.org/java-lang-integer-class-methods/)

`Integer`类将原始类型`int`的值包装到一个对象中。此类包含`int`类型字段。

## 构造方法

*   `Integer(int value)`：构造一个表示指定`int`值的`Integer`对象。
*   `Integer(String s)`：构造一个表示指定`String`值的`Integer`对象。

## Integer 类方法

### 1. `toBinaryString()`

`Integer.toBinaryString()`方法将参数的整数值转换为二进制表示的字符串形式。

**语法**

```java
public static String toBinaryString(int arg)
```

**参数**
`arg`：需要获取其二进制表示的整数参数。

**返回值**
参数的二进制表示形式。

### 2. `bitCount()`

`Integer.bitCount()`方法将参数的整数值转换为二进制字符串，然后返回其中`1`的个数。

**语法**

```java
public static int bitCount(int arg)
```

**参数**
`arg`：需要计算其`1`位个数的整数参数。

**返回值**
参数中存在的`1`位个数。

### 3. `toHexString()`

`Integer.toHexString()`方法将参数的整数值转换为十六进制表示的字符串形式。

**语法**

```java
public static String toHexString(int arg)
```

**参数**
`arg`：需要获取其十六进制表示的整数参数。

**返回值**
参数的十六进制表示形式。

### 4. `toOctalString()`

`Integer.toOctalString()`方法将参数的整数值转换为八进制表示的字符串形式。

**语法**

```java
public static String toOctalString(int arg)
```

**参数**
`arg`：需要获取其八进制表示的整数参数。

**返回值**
参数的八进制表示形式。

### 5. `parseXxx()`

`Integer.parseInt()`方法返回参数字符串值的原始数据类型。
基数`radix`表示字符串解析时使用的进制。

**语法**

```java
public static int parseInt(String arg)
              或
public static int parseInt(String arg, int radix)
```

**参数**
`arg`：要解析的字符串。
`radix`：进制数。

**返回值**
参数字符串值对应的原始数据类型。

## Java 示例代码

```java
// Java code explaining the Integer Class methods
// bitCount(), toBinaryString(), toHexString(), toOctalString(), parse__()
import java.lang.*;
public class NewClass
{
    public static void main(String args[])
    {
        int x = 15, count1, y = 128, count2;

        // Use of toBinaryString() method
        System.out.println("Binary string of 16 : "
                           + Integer.toBinaryString(x));
        System.out.println("Binary string of 100 : "
                           + Integer.toBinaryString(y));

        // Use of bitCount() method
        count1 = Integer.bitCount(x);
        System.out.println("\n 1's bit present in 16 : "+count1);

        count2 = Integer.bitCount(y);
        System.out.println(" 1's bit present in 100 : "+count2);

        // Use of toHexString() method
        System.out.println("\nHexadecimal string of 16 : "
                           + Integer.toHexString(x));
        System.out.println("Hexadecimal string of 100 : "
                           + Integer.toHexString(y));
        System.out.println("");

        // Use of toOctalString() method
        System.out.println("Octal string of 16 : "
                           + Integer.toOctalString(x));
        System.out.println("Octal string of 100 : "
                           + Integer.toOctalString(y) + "\n");

        // Use of parseInt() method
        int i1 =Integer.parseInt("34");
        int i2 = Integer.parseInt("15",8);
        double d = Double.parseDouble("54");

        System.out.println(i1);
        System.out.println(i2);
        System.out.println(d);
    }
}
```

**输出**

```java
Binary string of 16   : 1111
Binary string of 100  : 10000000

1's bit present in 16   : 4
 1's bit present in 100  : 1

Hexadecimal string of 16   : f
Hexadecimal string of 100  : 80

Octal string of 16   : 17
Octal string of 100  : 200

54.0
```

### 6. `hashCode()`

`Integer.hashCode()`方法返回传递的参数的`hashCode`值。

**语法**

```java
public int hashCode(arg)
```

**参数**
`arg`：需要获取其`hashCode`值的参数。

**返回值**
`arg`的`hashCode`值。

### 7. `lowestOneBit()`

`Integer.lowestOneBit()`方法首先将`int`转换为二进制，然后查找最低位的置位（`1`）位，并重置其余位。
例如：`arg = 36`
其二进制表示 = `0010 0100`
它考虑最低位（位于第3位），现在重置其余位，即 `0000 0100`
因此结果 = `0100` 即 `4`

**语法**

```java
public static int lowestOneBit(int arg)
```

**参数**
`arg`：传递的参数。

**返回值**
仅考虑参数中最低`1`位后的整数值。

### 8. `highestOneBit()`

`Integer.highestOneBit()`方法首先将`int`转换为二进制，然后查找最高位的置位（`1`）位，并重置其余位。
例如：`arg = 36`
其二进制表示 = `0010 0100`
它考虑最高位（位于第6位），现在重置其余位即 `0001 0000`
因此结果 = `10000` 即 `32`

**语法**

```java
public static int highestOneBit(int arg)
```

**参数**
`arg`：传递的参数。

**返回值**
仅考虑参数中最高`1`位后的整数值。

## Java 示例代码

```java
// Java program explaining Integer class methods
// hashcode(), lowestOneBit(), highestOneBit()
import java.lang.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of incrementExact() method
        int f1 = 30, f2 = -56;
        f1 = Integer.hashCode(f1);
        System.out.println("HashCode value of f1 : "+f1);

        f2 = Integer.hashCode(f2);
        System.out.println("HashCode value of f2 : "+f2);

        System.out.println("\nBinary representation of 30 : "
                           + Integer.toBinaryString(f1));

        // Use of lowestOneBit() method
        // Here it considers 00010 i.e. 2
        System.out.println("lowestOneBit of 30 : "
                           + Integer.lowestOneBit(f1));

        // Use of highestOneBit() method
        // Here it considers 10000 i.e. 16
        System.out.println("highestOneBit of 30 : "
                           + Integer.highestOneBit(f1));

    }
}
```

**输出**

```java
HashCode value of f1 : 30
HashCode value of f2 : -56

Binary representation of 30 : 11110
lowestOneBit of 30 : 2
highestOneBit of 30 : 16
```

### 9. `numberOfTrailingZeros()`

`Integer.numberOfTrailingZeros()`方法将`int`值转换为二进制，然后考虑最低的`1`位，并返回其后的零位数。
例如：`arg = 36`
其二进制表示 = `0010 0100`
它认为最低位（在第3位）即 `0000 0100`
所以结果 = `4`

**语法**

```java
public static int numberOfTrailingZeros(int arg)
```

**参数**
`arg`：参数。

**返回值**
最低位`1`位之后的零位个数。

### 10. `numberOfLeadingZeros()`

`Integer.numberOfLeadingZeros()`方法将`int`值转换为二进制，然后考虑最高的`1`位并返回其前面的零位数。
例如：`arg = 36`
其二进制表示 = `0010 0100`
它认为最高位（在第6位）即 `0010 0000`
所以结果 = `32–6` 即 `26`

**语法**

```java
public static int numberOfLeadingZeros(int arg)
```

**参数**
`arg`：参数。

**返回值**
最高位`1`位之前的零位个数。

### 11. `reverse()`

`Integer.reverse()`方法首先查找传递的参数的二进制补码，然后反转二进制补码中的比特顺序。

**语法**

```java
public static int reverse(int arg)
```

**参数**
`arg`：参数。

**返回值**
一个`int`值，其比特顺序是传递参数的二进制补码的逆序。

## Java 示例代码

```java
// Java program explaining Integer class methods
// numberOfTrailingZeros(), numberOfLeadingZeros(), reverse()
import java.lang.*;
public class NewClass
{
    public static void main(String[] args)
    {
        int f1 = 30;

        // Binary representation of int arg for your understanding
        System.out.println("Binary representation of 30 : "
                           + Integer.toBinaryString(f1));

        // Use of numberOfTrailingZeros() method
        // No. of zeros following 1 in 00010 = 1
        System.out.println("\nNo. Of Trailing Zeros : "
                           + Integer.numberOfTrailingZeros(f1));

        // Use of highestOneBit() method
        // No. of zeros following 1 in 10000 i.e. 32 - 5 = 27
        System.out.println("\nNo. Of Leading Zeros : "
                           + Integer.numberOfLeadingZeros(f1));

        // Use of Reverse() method
        System.out.println("\nReverse : " + Integer.reverse(f1));
    }
}
```

**输出**

```java
Binary representation of 30 : 11110

No. Of Trailing Zeros : 1
```

No. Of Leading Zeros  : 27

Reverse : 2013265920
```

本文由`莫希特·古普塔`供稿。如果你喜欢`GeeksforGeeks`并想投稿，你也可以使用[`write.geeksforgeeks.org`](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。