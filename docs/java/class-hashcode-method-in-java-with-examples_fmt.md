# Java 中的 `Class` 类 `hashCode()` 方法示例

> 原文：[https://www.geeksforgeeks.org/class-hashcode-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-hashcode-method-in-java-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 类的 `hashCode()` 方法用于获取此 `Class` 实例的哈希码表示。此方法返回一个整数值，即哈希码。

## 语法

```java
public int hashCode()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回一个整数值，即哈希码。

## 示例 1

下面的程序演示了 `hashCode()` 方法。

```java
// Java program to demonstrate hashCode() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        System.out.println("Class represented by c1: "
                         + c1);

        // hashCode method on c1
        System.out.println("HashCode value: "
                         + c1.hashCode());
    }
}
```

**输出：**

```
Class represented by c1: class java.lang.String
HashCode value: 589431969
```

## 示例 2

```java
// Java program to demonstrate hashCode() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = int.class;

        System.out.println("Class represented by c1: "
                         + c1);

        // hashCode method on c1
        System.out.println("HashCode value: "
                         + c1.hashCode());
    }
}
```

**输出：**

```
Class represented by c1: int
HashCode value: 589431969
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#hashCode--](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#hashCode--)