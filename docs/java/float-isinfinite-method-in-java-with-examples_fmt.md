# Java 中的 `Float isInfinite()` 方法，带示例

> 原文: [https://www.geeksforgeeks.org/float-isinfinite-method-in-java-with-examples/](https://www.geeksforgeeks.org/float-isinfinite-method-in-java-with-examples/)

[`Float`](https://www.geeksforgeeks.org/java-lang-float-class-in-java/) 类中的 `isInfinite()` 方法是 Java 中的一个内置方法，如果这个 `Float` 值或指定的 `Float` 值在数量级上无限大，则返回 `true`，否则返回 `false`。

**语法:**
```java
public boolean isInfinite()
        or
public static boolean isInfinite(float val)
```

**参数**: 该函数接受单个参数 `val`，该值指定了当直接使用 `Float` 类作为静态方法调用时要检查的值。当方法用作实例方法时，参数不是必需的。
**返回值:** 返回 `true` 如果值为无穷大，则返回 `false`。

下面的程序说明了 Java 中的 `isInfinite()` 方法:

### 示例 1: 使用静态 `isInfinite()` 方法

```java
// Java code to demonstrate
// Float isInfinite() method
// without parameter

class GFG {
    public static void main(String[] args)
    {

// first example
        Float f1 = new Float(1.0 / 0.0);

        boolean res = f1.isInfinite();

// printing the output
        if (res)
            System.out.println(f1
                               + " is infinity");
        else
            System.out.println(f1
                               + " is not infinity");

// second example
        f1 = new Float(0.0 / 0.0);

        res = f1.isInfinite();

// printing the output
        if (res)
            System.out.println(f1
                               + " is infinity");
        else
            System.out.println(f1
                               + " is not infinity");
    }
}
```

**输出:**
```java
Infinity is infinity
NaN is not infinity
```

### 示例 2: 使用非静态 `isInfinite()` 方法

```java
// Java code to demonstrate
// Float isInfinite() method
// with parameter

class GFG {
    public static void main(String[] args)
    {

// first example
        Float f1 = new Float(1.0 / 0.0);

        boolean res = f1.isInfinite(f1);

// printing the output
        if (res)
            System.out.println(f1
                               + " is infinity");
        else
            System.out.println(f1
                               + " is not infinity");

// second example
        f1 = new Float(0.0 / 0.0);

        res = f1.isInfinite(f1);

// printing the output
        if (res)
            System.out.println(f1
                               + " is infinity");
        else
            System.out.println(f1
                               + " is not infinity");
    }
}
```

**输出:**
```java
Infinity is infinity
NaN is not infinity
```

**参考:** [https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#isInfinite()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#isInfinite())