# Java 中的构造函数 getAnnotatedReturnType() 方法示例

> 原文：[https://www.geeksforgeeks.org/constructor-getannotatedreturntype-method-in-java-with-examples/](https://www.geeksforgeeks.org/constructor-getannotatedreturntype-method-in-java-with-examples/)

[`Constructor`](https://www.geeksforgeeks.org/constructors-in-java/) 类的 `getAnnotatedReturnType()` 方法用于返回一个表示注释类型的 `AnnotatedType` 对象，以指定构造函数对象的返回类型。返回的 `AnnotatedType` 表示 `AnnotatedType` 本身或其任何子接口（如 `AnnotatedArrayType`、`AnnotatedParameterizedType`、`AnnotatedTypeVariable`、`AnnotatedWildcardType`）的实现。`AnnotatedType` 表示任何类型的潜在注释使用，包括数组类型、参数化类型、类型变量或 Java 虚拟机中当前运行的通配符类型。

## 语法

```java
public AnnotatedType getAnnotatedReturnType()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回一个 `AnnotatedType` 对象，代表该可执行文件所代表的方法或构造函数的返回类型。

## 程序 1

下面的程序说明了 `getAnnotatedReturnType()` 方法：

```java
// Java program to demonstrate
// Constructor.getAnnotatedReturnType() method

import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;
import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Constructor;
import java.util.Arrays;

public class GFG {

    // main method
    public static void main(String[] args)
    {

        try {
            // create class object
            Class demo = Demo.class;

            // get Constructor object array
            // from the class object
            Constructor[] cons
                = demo.getConstructors();

            // get AnnotatedType for return type
            AnnotatedType annotatedType
                = cons[0]
                      .getAnnotatedReturnType();

            System.out.println(
                "Type: "
                + annotatedType
                      .getType()
                      .getTypeName());

            System.out.println(
                "Annotations: "
                + Arrays.toString(
                      annotatedType.getAnnotations()));
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}

class Demo {

    // AnnotatedType is @customAnnotatedType
    public @customAnnotatedType Demo()
    {
        // do stuffs
    }
}

// Creating custom AnnotatedType
@Target({ ElementType.TYPE_USE })
@Retention(RetentionPolicy.RUNTIME)
@interface customAnnotatedType {
}
```

**输出：**

```java
Type: Demo
Annotations: [@customAnnotatedType()]
```

## 程序 2

```java
// Java program to demonstrate
// Constructor.getAnnotatedReturnType() method

import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;
import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Constructor;
import java.util.Arrays;

public class GFG {

    // main method
    public static void main(String[] args)
    {

        try {
            // create class object
            Class shape = Shape.class;

            // get Constructor object array
            // from the class object
            Constructor[] cons
                = shape.getConstructors();

            // get AnnotatedType for return type
            AnnotatedType annotatedType
                = cons[0]
                      .getAnnotatedReturnType();

            System.out.println(
                "Type: "
                + annotatedType
                      .getType()
                      .getTypeName());

            System.out.println(
                "Annotations: "
                + Arrays.toString(
                      annotatedType.getAnnotations()));
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}

class Shape {

    // AnnotatedType is @customAnnotatedType
    public @ShapeProperties Shape()
    {
        // do stuffs
    }
}

// Creating custom AnnotatedType
@Target({ ElementType.TYPE_USE })
@Retention(RetentionPolicy.RUNTIME)
@interface ShapeProperties {
}
```

**输出：**

```java
Type: Shape
Annotations: [@ShapeProperties()]
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getAnnotatedReturnType()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getAnnotatedReturnType())