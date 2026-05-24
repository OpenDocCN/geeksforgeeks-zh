# Class.getField()方法详解

> 原文：[https://www.geeksforgeeks.org/class-getfield-method-in-java-with-examples/](https://www.geeksforgeeks.org/class-getfield-method-in-java-with-examples/)

[`java.lang.Class`](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)类的`getField()`方法用于获取该类的指定字段，该字段必须是公共字段及其成员。方法以字段对象的形式返回此类的指定字段。

## 语法

```java
public Field getField(String fieldName)
       throws NoSuchFieldException,
              SecurityException
```

## 参数

该方法接受一个参数`fieldName`，即要获取的字段名。

## 返回值

该方法以`Field`对象的形式返回该类的指定字段。

## 异常

如果找不到指定名称的字段，该方法抛出：
*   `NoSuchFieldException`
*   `NullPointerException`：如果名称为空。
*   如果存在安全管理器且安全条件不满足，则抛出`SecurityException`。

以下程序演示了`getField()`方法。

### 示例 1

```java
// Java program to demonstrate getField() method

import java.util.*;

public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException, NoSuchFieldException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        String fieldName = "obj";

        // Get the field of myClass
        // using getField() method
        System.out.println(
            fieldName + " Field of myClass: "
            + myClass.getField(fieldName));
    }
}
```

**输出：**

```java
Class represented by myClass: class Test
obj Field of myClass: public java.lang.Object Test.obj
```

### 示例 2

```java
// Java program to demonstrate getField() method

import java.util.*;

class Main {

    private Object obj;

    Main()
    {

        class Arr {
        };

        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException, NoSuchFieldException
    {
        Main t = new Main();

        // returns the Class object
        Class myClass = t.obj.getClass();

        String fieldName = "obj";

        try {
            // Get the field of myClass
            // using getField() method
            System.out.println(
                fieldName + " Field of myClass: "
                + myClass.getField(fieldName));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
java.lang.NoSuchFieldException: obj
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getField-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getField-java.lang.String-)