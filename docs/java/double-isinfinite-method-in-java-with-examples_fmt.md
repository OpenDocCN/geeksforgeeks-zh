# Java 中的 `Double.isInfinite()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/double-isinfinite-method-in-java-with-examples/](https://www.geeksforgeeks.org/double-isinfinite-method-in-java-with-examples/)

[`Double`](https://www.geeksforgeeks.org/java-lang-double-class-java/) 类的 `Double.isInfinite()` 方法是 Java 中的内置方法，如果该 `Double` 值或指定的 `Double` 值在数量级上无限大，则返回 `true`，否则返回 `false`。

**语法：**

```java
public boolean isInfinite()
        or
public static boolean isInfinite(double val)
```

**参数：** 该函数接受单个参数 `val`，该值指定了当直接使用 `Double` 类作为静态方法调用时要检查的值。当方法用作实例方法时，参数不是必需的。
**返回值：** 返回 `true` 如果值为无穷大，则返回 `false`。

下面的程序说明了 Java 中的 `isInfinite()` 方法：

## 示例代码

```java
// Java code to demonstrate
// Double isInfinite() method
// without parameter

class GFG {
    public static void main(String[] args)
    {

// first example
        Double f1 = new Double(1.0 / 0.0);

        boolean res = f1.isInfinite();

// printing the output
        if (res)
            System.out.println(f1 + " is infinity");
        else
            System.out.println(f1 + " is not infinity");

// second example
        f1 = new Double(0.0 / 0.0);

        res = f1.isInfinite();

// printing the output
        if (res)
            System.out.println(f1 + " is infinity");
        else
            System.out.println(f1 + " is not infinity");
    }
}
```

**输出：**

```java
Infinity is infinity
NaN is not infinity
```