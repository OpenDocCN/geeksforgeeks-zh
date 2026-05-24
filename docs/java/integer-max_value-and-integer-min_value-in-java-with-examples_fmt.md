# Integer.MAX_VALUE 和 Integer.MIN_VALUE 在 Java 中的示例

> 原文：[https://www.geeksforgeeks.org/integer-max_value-and-integer-min_value-in-java-with-examples/](https://www.geeksforgeeks.org/integer-max_value-and-integer-min_value-in-java-with-examples/)

很多时候，在[竞技编程](https://www.geeksforgeeks.org/how-to-begin-with-competitive-programming/)中，需要给变量赋值数据类型能容纳的最大或最小值，但是记住这么大又精确的数字是一件困难的工作。因此，Java 有常数来表示这些数字，这样就可以直接将这些数字赋给变量，而无需实际键入整数。

`Integer.MAX_VALUE` 是 `Integer` 类（属于 `java.lang` 包）中的一个常数，它指定了 Java 中任何整型变量可以存储的最大可能值。其实际值为：

```java
2^31-1 = 2147483647
```

## 示例 1

```java
// Java program to show
// the value of Integer.MAX_VALUE

class GFG {

    // Driver code
    public static void main(String[] arg)
    {
        // Print the value of Integer.MAX_VALUE
        System.out.println("Integer.MAX_VALUE = "
                           + Integer.MAX_VALUE);
    }
}
```

## 输出

```java
Integer.MAX_VALUE = 2147483647
```