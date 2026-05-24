# Class.isPrimitive() 方法详解

> 原文: [https://www.geeksforgeeks.org/class-isprimitive-method-in-with-examples/](https://www.geeksforgeeks.org/class-isprimitive-method-in-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 的 `isPrimitive()` 方法，用来检查这个类是否是原始类型（Primitive）类。如果此类是原始类型类，则方法返回 `true`。否则返回 `false`。

**语法:**
```java
public boolean isPrimitive()
```

**参数:** 此方法不接受任何参数。
**返回值:** 如果这个类是原始类型类，这个方法返回 `true`。否则返回 `false`。

下面的程序演示了 `isPrimitive()` 方法。

**示例 1:**
```java
// Java program to demonstrate isPrimitive() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an primitive
        // using isPrimitive() method
        System.out.println("Is Test a primitive: "
                           + myClass.isPrimitive());
    }
}
```
**Output:**
```java
Class represented by myClass: class Test
Is Test a primitive: false
```

**示例 2:**
```java
// Java program to demonstrate isPrimitive() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = int.class;

        // Check if myClass is an primitive
        // using isPrimitive() method
        System.out.println("Is myClass a primitive: "
                           + myClass.isPrimitive());
    }
}
```
**Output:**
```java
Is myClass a primitive: true
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isPrimitive--](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isPrimitive--)