# 检查给定类是否是本地内部类的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-check-if-a-given-class-is-a-local-inner-class/](https://www.geeksforgeeks.org/java-program-to-check-if-a-given-class-is-a-local-inner-class/)

[局部内部类](https://www.geeksforgeeks.org/local-inner-class-java/)是在块内声明的类。这些类仅在块内可见。因此，您需要在块中实例化该类。有时，这个块可以用于循环或 `if-else` 子句。这些类可以访问包含它的类的字段。本地内部类必须在定义它们的块中实例化。

我们将讨论如何使用以下方法来检查给定的类是否是[局部内部类](https://www.geeksforgeeks.org/local-inner-class-java/)。

**方法 1：**

*   要检查一个类是否是本地内部类，`java.lang.Class` 提供了一个名为 [`isLocalClass()`](https://www.geeksforgeeks.org/class-islocalclass-method-in-java-with-examples/) 的方法。
*   此方法如果给定的类是局部的，则返回 `true`，否则返回 `false`。注意 `isLocalClass()` 定义在 `java.lang.Class` 类中。因此，必须首先调用对象的 `getClass()` 方法。
*   此方法返回一个表示该对象类的 `Class` 实例。参见以下代码：

```java
// Java program to check if a class is inner
// local class using isLocalClass() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        class LocalInnerClass {
            // This is a local inner class
        }
        // Creating a LocalInnerClass object
        LocalInnerClass inner = new LocalInnerClass();

        // Getting the Class instance associated with
        // the class of inner(i.e. LocalInnerClass)
        // which is returned by getClass() method of inner
        Class localClass = inner.getClass();

        // isLocalClass() method of localClass returns true
        // if and only if localClass is a Local Class
        System.out.println(
            "Is inner a local class object? :"
            + localClass.isLocalClass());
    }
}
```

**输出**

```java
Is inner a local class object? :true
```