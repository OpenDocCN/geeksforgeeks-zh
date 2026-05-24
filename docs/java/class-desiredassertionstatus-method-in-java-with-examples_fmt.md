# Java 中的 Class 类的 desiredAssertionStatus() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/class-desiredassertionstatus-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-desiredassertionstatus-method-in-java-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 类的 `desiredAssertionStatus()` 方法用于获取该类的断言状态，当调用该方法时，该断言状态将被分配给该类。方法以布尔值的形式返回该类的断言状态。

## 语法

```java
public boolean desiredAssertionStatus()
```

## 参数
该方法不接受任何参数。

## 返回值
该方法以布尔值的形式返回该类的指定断言状态。

下面的程序演示了 `desiredAssertionStatus()` 方法。

## 例 1

```java
// Java program to demonstrate
// desiredAssertionStatus() method

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

        // Get the Assertion Status of myClass
        // using desiredAssertionStatus() method
        System.out.println("Assertion Status of myClass: "
                           + myClass.desiredAssertionStatus());
    }
}
```

## 输出

```java
Class represented by myClass: class Test
Assertion Status of myClass: false
```

## 例 2

```java
// Java program to demonstrate
// desiredAssertionStatus() method

import java.util.*;

class Main {

    private Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException, NoSuchFieldException
    {

        try {

            // returns the Class object for this class
            Class myClass = Class.forName("Main");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            // Get the Assertion Status of myClass
            // using desiredAssertionStatus() method
            System.out.println("Assertion Status of myClass: "
                               + myClass.desiredAssertionStatus());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## 输出

```java
Class represented by myClass: class Main
Assertion Status of myClass: false
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#desiredAssertionStatus--](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#desiredAssertionStatus--)