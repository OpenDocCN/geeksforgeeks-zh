# Java 中的类 toGenericString()方法，带示例

> 原文：[`https://www.geeksforgeeks.org/class-togenericstring-method-in-java-with-examples/`](https://www.geeksforgeeks.org/class-togenericstring-method-in-java-with-examples/)

## 概述

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 类的 [`toGenericString()`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 方法用于将该类的实例转换为字符串表示形式，以及关于修饰符和类型参数的信息。此方法返回形成的字符串表示形式。

## 语法

```java
public String toGenericString()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回这个对象的字符串表示。

下面的程序演示了 [`toGenericString()`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 方法。

## 示例 1

```java
// Java program to demonstrate toGenericString() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        System.out.print("Class represented by c1: ");

        // toGenericString method on c1
        System.out.println(c1.toGenericString());
    }
}
```

## 输出

```java
Class represented by c1: public final class java.lang.String
```

## 示例 2

```java
// Java program to demonstrate toGenericString() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c2 = int.class;
        Class c3 = void.class;

        System.out.print("Class represented by c2: ");

        // toGenericString method on c2
        System.out.println(c2.toGenericString());

        System.out.print("Class represented by c3: ");

        // toGenericString method on c3
        System.out.println(c3.toGenericString());
    }
}
```

## 输出

```java
Class represented by c2: int
Class represented by c3: void
```

## 参考

[`https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#toGenericString--`](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#toGenericString--)