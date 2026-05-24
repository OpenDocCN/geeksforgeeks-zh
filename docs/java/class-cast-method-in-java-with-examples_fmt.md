# Java 中的 `cast()` 方法示例

> 原文：[https://www.geeksforgeeks.org/class-cast-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-cast-method-in-java-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 类的 `cast()` 方法用于将指定的对象强制转换为该类的对象。方法在以对象的形式强制转换后返回对象。

## 语法

```java
public T[] cast(Object obj)
```

## 参数

该方法接受一个参数 `obj`，该对象将被投射。

## 返回值

该方法以对象的形式铸造后返回指定的 `obj`。

## 异常

如果对象不为空且不可分配给类型 `T`，则此方法抛出：

*   `ClassCastException`

下面的程序演示了 `cast()` 方法。

### 示例 1

```java
// Java program to demonstrate
// cast() method

import java.util.*;

public class Test {

    public static Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Cast the object obj to object of myClass
        // using cast() method
        System.out.println("Object " + obj + " after cast "
                           + "upon to class Test: "
                           + myClass.cast(obj));
    }
}
```

**输出：**

```java
Class represented by myClass: class Test
Object null after cast upon to class Test: null
```

### 示例 2

```java
// Java program to demonstrate
// cast() method

import java.util.*;

class Main {

    private static int obj = 10;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        try {
            // returns the Class object for this class
            Class myClass = Class.forName("Main");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            // Cast the object obj to object of myClass
            // using cast() method
            System.out.println("Object " + obj + " after cast "
                               + "upon to class Test: "
                               + myClass.cast(obj));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
Class represented by myClass: class Main
java.lang.ClassCastException: Cannot cast java.lang.Integer to Main
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#cast-java.lang.Object-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#cast-java.lang.Object-)