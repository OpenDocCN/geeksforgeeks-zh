# Java 中的 Boolean.compare() 方法示例

> 原文：[https://www.geeksforgeeks.org/boolean-compare-method-in-java-with-examples/](https://www.geeksforgeeks.org/boolean-compare-method-in-java-with-examples/)

[`Boolean`](https://www.geeksforgeeks.org/java-lang-boolean-class-java/) 类的 `compare()` 方法是 Java 中的内置方法，用于比较两个布尔值。这是一个静态方法，因此可以在不创建 [`Boolean`](https://www.geeksforgeeks.org/java-lang-boolean-class-java/) 类的任何对象的情况下调用，即直接使用类名。

## 语法

```java
Boolean.compare(boolean a, boolean b)
```

## 参数

该方法接受两个待比较的布尔值参数 `a` 和 `b`。

## 返回值

该方法的返回类型为 `int`。它返回：

*   如果 `a` 等于 `b`，则为 0。
*   如果 `a` 为 `false`，`b` 为 `true`，则为负值。
*   如果 `a` 为 `true`，`b` 为 `false`，则为正值。

下面是说明 `Boolean` 类的 `compare()` 方法的程序：

### 程序 1

```java
// Java code to implement
// compare() method of Boolean class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {
        // first value
        boolean a = true;

        // second value
        boolean b = true;

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + Boolean.compare(a, b));
    }
}
```

**输出：**

```java
true comparing with true = 0
```

### 程序 2

```java
// Java code to implement
// compare() method of Java class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {
        // first value
        boolean a = true;

        // second value
        boolean b = false;

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + Boolean.compare(a, b));
    }
}
```

**输出：**

```java
true comparing with false = 1
```

### 程序 3

```java
// Java code to implement
// compare() method of Java class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {
        // first value
        boolean a = false;

        // second value
        boolean b = true;

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + Boolean.compare(a, b));
    }
}
```

**输出：**

```java
false comparing with true = -1
```