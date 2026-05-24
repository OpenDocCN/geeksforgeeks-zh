# Java中Class.getResourceAsStream()方法详解

> 原文：[https://www.geeksforgeeks.org/class-getresourceasstream-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-getresourceasstream-method-in-java-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)类的`getResourceAsStream()`方法用于获取该类指定资源的资源。该方法以`InputStream`对象的形式返回此类的指定资源。

## 语法

```java
public InputStream getResourceAsStream(String resourceName)
```

## 参数

此方法接受一个参数`resourceName`，即要获取的资源的名称。

## 返回值

该方法以`InputStream`对象的形式返回该类的指定资源。

## 异常

此方法抛出：
*   `NullPointerException`：如果名称为空。

## 示例

下面的程序演示了`getResourceAsStream()`方法。

### 例1

```java
// Java program to demonstrate
// getResourceAsStream() method

import java.util.*;

public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        String resourceName = "obj";

        // Get the resource of myClass
        // using getResourceAsStream() method
        System.out.println(
            resourceName + " resource of myClass: "
            + myClass.getResourceAsStream(resourceName));
    }
}
```

**输出：**

```java
Class represented by myClass: class Test
obj resource of myClass: null
```

### 例2

```java
// Java program to demonstrate
// getResourceAsStream() method

import java.util.*;

class Main {

    private Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException, NoSuchFieldException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Main");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        String resourceName = "obj";

        try {
            // Get the resource of myClass
            // using getResourceAsStream() method
            System.out.println(
                resourceName + " resource of myClass: "
                + myClass.getResourceAsStream(resourceName));
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
obj resource of myClass: null
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getResourceAsStream-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getResourceAsStream-java.lang.String-)