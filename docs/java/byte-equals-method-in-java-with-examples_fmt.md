# Java中的Byte equals()方法示例

> 原文：[https://www.geeksforgeeks.org/byte-equals-method-in-java-with-examples/](https://www.geeksforgeeks.org/byte-equals-method-in-java-with-examples/)

[`Byte`](https://www.geeksforgeeks.org/java-lang-byte-class-java/)类的`equals()`方法是Java中的一个内置方法，用于比较给定对象的等式和调用`equals()`方法的`Byte`实例。

## 语法

```java
ByteObject.equals(Object a)
```

## 参数
它将一个对象类型对象`a`作为输入，与调用`equals()`方法的`Byte`对象的实例进行比较。

## 返回值
返回一个`boolean`值。如果`a`的值等于`ByteObject`的值，则返回`true`。

下面是`equals()`方法在Java中的实现：

### 例1

```java
// Java code to demonstrate
// Byte equals() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Byte object
        Byte a = new Byte("20");

        // creating a Byte object
        Byte b = new Byte("20");

        // equals method in Byte class
        boolean output = a.equals(b);

        // Printing the output
        System.out.println("Does " + a + " equals "
                           + b + " : " + output);
    }
}
```

**Output:**

```java
Does 20 equals 20 : true
```

### 例2

```java
// Java code to demonstrate
// Byte equals() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Byte object
        Byte a = new Byte("2");

        // creating a Byte object
        Byte b = new Byte("20");

        // equals method in Byte class
        boolean output = a.equals(b);

        // Printing the output
        System.out.println("Does " + a + " equals "
                           + b + " : " + output);
    }
}
```

**Output:**

```java
Does 2 equals 20 : false
```