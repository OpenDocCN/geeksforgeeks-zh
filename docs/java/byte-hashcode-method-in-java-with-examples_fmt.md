# Java 中的 Byte hashCode()方法，带示例

> 原文：[https://www.geeksforgeeks.org/byte-hashcode-method-in-java-with-examples/](https://www.geeksforgeeks.org/byte-hashcode-method-in-java-with-examples/)

[`Byte`](https://www.geeksforgeeks.org/java-lang-byte-class-java/)类的 `hashCode()` 方法是 Java 中的内置方法，用于返回 `Byte` 对象的哈希代码。

**注意：** `hashCode()` 返回的值与 `intValue()` 相同。

## 语法

```java
ByteObject.hashCode()
```

## 返回值

它返回一个 `int` 值，代表指定字节对象的哈希码。

下面是 `hashCode()` 方法在 Java 中的实现：

## 示例

### 例 1

```java
// Java code to demonstrate
// Byte hashCode() method

class GFG {
    public static void main(String[] args)
    {

        String value = "74";

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

        // hashCode of the Byte Object
        int output = b.hashCode();

        // printing the output
        System.out.println("HashCode of "
                           + b + " : " + output);
    }
}
```

**输出：**

```java
HashCode of 74 : 74
```

### 例 2

```java
// Java code to demonstrate
// Byte hashCode() method

class GFG {
    public static void main(String[] args)
    {

        String value = "-17";

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

        // hashCode of the Byte Object
        int output = b.hashCode();

        // printing the output
        System.out.println("HashCode of "
                           + b + " : " + output);
    }
}
```

**输出：**

```java
HashCode of -17 : -17
```