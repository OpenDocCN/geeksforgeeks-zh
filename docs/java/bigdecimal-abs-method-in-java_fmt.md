# Java 中的 BigDecimal abs()方法

> 原文: [https://www.geeksforgeeks.org/bigdecimal-abs-method-in-java/](https://www.geeksforgeeks.org/bigdecimal-abs-method-in-java/)

## 1. `BigDecimal abs()`

`java.math.BigDecimal.abs()` 用于返回一个 `BigDecimal`，其值是此 `BigDecimal` 的绝对值，且标度（scale）为 `this.scale()`。

**语法:**

```java
public BigDecimal abs()
```

**参数:** 该方法不接受任何参数。

**返回值:** 返回一个 `BigDecimal`，其值是此 `BigDecimal` 的绝对值，小数位数是 `this.scale()`。

下面的程序将说明 `java.math.BigDecimal.abs()` 方法的使用:

**程序 1**

```java
// Java program to demonstrate abs() method
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigDecimal object
        BigDecimal num;

        // Assigning value to num
        num = new BigDecimal("-51");

        // Displaying the result
        System.out.println("Absolute value is " + num.abs());
    }
}
```

**Output:**

```java
Absolute value is 51
```

**程序 2**

```java
// Java program to demonstrate abs() method
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // creating a BigDecimal object
        BigDecimal num;

        // assign value to num
        num = new BigDecimal("-63.93471");

        System.out.println("Absolute value is " + num.abs());
    }
}
```

**Output:**

```java
Absolute value is 63.93471
```

## 2. `BigDecimal abs(MathContext mc)`

`java.math.BigDecimal.abs(MathContext mc)` 返回一个 `BigDecimal`，其值是根据 `MathContext` 对象 `mc` 指定的精度设置进行舍入后得到的此 `BigDecimal` 的绝对值。

**语法:**

```java
public BigDecimal abs(MathContext mc)
```

**参数:** 该函数只接受 `MathContext` 类对象的一个参数 `mc`，该参数指定了用于舍入的精度设置。

**返回值:** 返回一个 `BigDecimal`，其值是根据对象 `mc` 指定的精度设置取整得到的此 `BigDecimal` 的绝对值。

**异常:** 如果结果不精确但舍入模式不必要，则该方法抛出 `ArithmeticException`。

下面的程序用指定的数学上下文说明了 `java.math.BigDecimal.abs()` 方法的使用:

**程序 1**

```java
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create 2 BigDecimal objects
        BigDecimal num, absv;

        MathContext mc = new MathContext(2);

        // Assign value to num
        num = new BigDecimal("51.93471");

        // Assign absolute value of num to absv rounded
        // to 2 precision using mc
        absv = num.abs(mc);

        System.out.println("Absolute value, rounded to 2 precision is "
                           + absv);
    }
}
```

**Output:**

```java
Absolute value, rounded to 2 precision is 52
```

**程序 2**

```java
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create 2 BigDecimal objects
        BigDecimal num, absv;

        MathContext mc = new MathContext(15);

        // Assign value to num
        num = new BigDecimal("143567812363.93471");

        // Assign absolute value of num to absv rounded
        // to 15 precision using mc
        absv = num.abs(mc);

        System.out.println("Absolute value, rounded to 15 precision is "
                           + absv);
    }
}
```

**Output:**

```java
Absolute value, rounded to 15 precision is 143567812363.935
```

**参考:** [https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#abs()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#abs())