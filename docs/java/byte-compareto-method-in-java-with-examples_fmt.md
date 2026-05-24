# Java 中的 `Byte` `compareTo()` 方法，带示例

> 原文：`https://www.geeksforgeeks.org/byte-compareto-method-in-java-with-examples/`

[`Byte`](https://www.geeksforgeeks.org/java-lang-byte-class-java/) 类的 `compareTo()` 方法是 Java 中的内置方法，用于将给定的字节类型对象与调用 `compareTo()` 方法的 `Byte` 实例进行比较。

## 语法

```java
ByteObject.compareTo(Byte a)
```

## 参数
它将 `Byte` 类型对象 `a` 作为输入，该输入将与调用 `compareTo` 方法的 `Byte` 对象的实例进行比较。

## 返回值
返回一个 `int` 值。它返回：
*   0 如果 `a` 等于 `b`
*   正值 `a` 大于 `b`
*   负值 `b` 大于 `a`

下面是 `compareTo()` 方法在 Java 中的实现：

## 示例 1

```java
// Java code to demonstrate
// Byte compareTo() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Byte object
        Byte a = new Byte("20");

        // creating a Byte object
        Byte b = new Byte("20");

        // compareTo method in Byte class
        int output = a.compareTo(b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**输出：**

```java
Comparing 20 and 20 : 0
```

## 示例 2

```java
// Java code to demonstrate
// Byte compareTo() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Byte object
        Byte a = new Byte("20");

        // creating a Byte object
        Byte b = new Byte("10");

        // compareTo method in Byte class
        int output = a.compareTo(b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**输出：**

```java
Comparing 20 and 10 : 10
```

## 示例 3

```java
// Java code to demonstrate
// Byte compareTo() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Byte object
        Byte a = new Byte("10");

        // creating a Byte object
        Byte b = new Byte("20");

        // compareTo method in Byte class
        int output = a.compareTo(b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**输出：**

```java
Comparing 10 and 20 : -10
```