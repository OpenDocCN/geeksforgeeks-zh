# Java 中的 Byte toString()方法，带示例

> 原文:[https://www.geeksforgeks.org/byte-tostring-method-in-java-with-examples/](https://www.geeksforgeks.org/byte-tostring-method-in-java-with-examples/)

[`Byte`](https://www.geeksforgeeks.org/java-lang-byte-class-java/)类的`toString()`方法是 Java 中的一个内置方法，用于返回字符串值。

### `public String toString()`

**语法:**

```java
ByteObject.toString()
```

**返回值:** 返回一个`String`对象，其值等于`ByteObject`的值。

下面是`toString()`方法的实现:

Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to implement
// toString() method of Byte class

class GFG {
    public static void main(String[] args)
    {

        // byte value
        byte value = 19;

        // creating a byte Object
        Byte b = new Byte(value);

        // toString() method in Byte class
        String output = b.toString();

        // printing the output
        System.out.println(output);
    }
}
```

**Output:**

```java

```