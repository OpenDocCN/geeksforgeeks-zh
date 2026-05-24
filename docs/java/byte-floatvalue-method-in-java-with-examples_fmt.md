# Java 中的 `Byte.floatValue()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/byte-floatvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/byte-floatvalue-method-in-java-with-examples/)

[`Byte`](https://www.geeksforgeeks.org/java-lang-byte-class-java/) 类的 `floatValue()` 方法是 Java 中的一个内置方法，用于将这个 `Byte` 对象的值作为 `float` 返回。

## 语法

```java
ByteObject.floatValue()
```

## 返回值
将字节对象的值作为 `float` 返回。

下面是 `floatValue()` 方法在 Java 中的实现：

## 例 1

```java
// Java code to demonstrate
// Byte floatValue() method

class GFG {
    public static void main(String[] args)
    {

// byte value
        byte a = 17;

// wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(a);

// floatValue of the Byte Object
        float output = b.floatValue();

// printing the output
        System.out.println("Float value of "
                           + a + " is : " + output);
    }
}
```

**Output:**

```java
Float value of 17 is : 17.0
```

## 例 2

```java
// Java code to demonstrate
// Byte floatValue() method

class GFG {
    public static void main(String[] args)
    {

String value = "17";

// wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

// floatValue of the Byte Object
        float output = b.floatValue();

// printing the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Float value of 17 is : 17.0
```