# Java 中的 `BigInteger` `max()`和`min()`方法

> 原文: [https://www.geeksforgeeks.org/biginteger-max-and-min-methods-in-java/](https://www.geeksforgeeks.org/biginteger-max-and-min-methods-in-java/)

先决条件: [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

## `BigInteger` `max()` 方法

`BigInteger` 类的 `max()` 方法返回一个 `BigInteger`，其值是当前 `BigInteger` 与作为参数传递给该方法的 `BigInteger` 中较大的那个。如果两个值相等，则可以返回其中任何一个。

`BigInteger` 类上有一个类似的方法 `compareTo()`。`max()` 方法与 `compareTo()` 的不同之处在于，在 `compareTo()` 方法中，我们必须解释结果，而在 `max` 方法中，已经返回了最大的 `BigInteger`。

### 语法

```java
public BigInteger max(BigInteger val)
```

### 参数

该方法接受一个参数 `val`，该值是要计算最大值的值。

### 返回值

该方法返回 `BigInteger`，其值是这个和 `val` 中的较大值。如果它们相等，任何一个都可以返回。

下面的程序说明了 `BigInteger` 类的 `max()` 方法。

```java
/*
 * Program Demonstrate max() method of BigInteger 
 */
import java.math.*;

public class GFG {

    public static void main(String[] args) {

        // Create 2 BigInteger objects
        BigInteger biginteger = new BigInteger("8976543245");
        BigInteger val = new BigInteger("9248040402");

        // Call max() method to find greater value
        // between two BigIntegers.
        BigInteger biggerInteger = biginteger.max(val);

        String result = "Bigger Integer between " + biginteger + " and "
                + val + " is " + biggerInteger;

        // Prints the result 
        System.out.println(result);

    }
}
```

**输出:**

```java
Bigger Integer between 8976543245 and 9248040402 is 9248040402
```

## `BigInteger` `min()` 方法

`BigInteger` 类的 `min()` 方法返回一个 `BigInteger`，其值是当前 `BigInteger` 与作为参数传递给该方法的 `BigInteger` 中较小的那个。如果两个值相等，则可以返回其中任何一个。

`BigInteger` 类上有一个类似的方法 `compareTo()`。`min()` 方法与 `compareTo()` 的不同之处在于，在 `compareTo()` 方法中，我们必须解释结果，而在 `min()` 方法中，将返回最小的 `BigInteger`。

### 语法

```java
public BigInteger min(BigInteger val)
```

### 参数

该方法接受一个参数 `val`，该值是指要计算最小值的值。

### 返回值

该方法返回大整数，该大整数的值是这个和 `val` 中较小的一个。如果两个值相等，则可以返回其中任何一个。

下面的程序说明了 `BigInteger` 类的 `min()` 方法。

```java
/*
 * Program Demonstrate min() method of BigInteger 
 */
import java.math.*;

public class GFG {

    public static void main(String[] args) {

        // Create 2 BigInteger objects
        BigInteger biginteger = new BigInteger("5782539631");
        BigInteger val = new BigInteger("3592633823");

        // Call min() method to find lesser value
        // between two BigIntegers.
        BigInteger biggerInteger = biginteger.min(val);

        String result = "lesser Integer between " + biginteger + " and "
                + val + " is " + biggerInteger;

        // Prints the result 
        System.out.println(result);

    }
}
```

**输出:**

```java
lesser Integer between 5782539631 and 3592633823 is 3592633823
```

**参考:**

*   [https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#max(java.math.BigInteger)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#max(java.math.BigInteger))
*   [https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#min(java.math.BigInteger)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#min(java.math.BigInteger))