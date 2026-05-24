# `AnnotatedElement`接口的`isAnnotationPresent()`方法详解

> 原文：[https://www.geeksforgeeks.org/annotatedelement-isannotationpresent-method-in-java-with-examples/](https://www.geeksforgeeks.org/annotatedelement-isannotationpresent-method-in-java-with-examples/)

`java.lang.AnnotatedElement`类的`isAnnotationPresent()`方法用于检查实现此接口的类中是否存在指定注释类型的注释。方法返回一个表示相同内容的布尔值。

## 语法：
```java
public boolean isAnnotationPresent(Class<T> annotationClass)
```

## 参数：
该方法接受一个参数`annotationClass`，即要获取的标注类型。

## 返回值：
该方法返回`布尔值`表示相同。

## 异常：
此方法抛出：
*   `NullPointerException`：如果给定的注释类为空。

下面的程序演示了`isAnnotationPresent()`方法。

### 例 1：
```java
// Java program to demonstrate
// isAnnotationPresent() method

import java.util.*;
import java.lang.reflect.*;
import java.lang.annotation.*;

// create a custom Annotation
@Retention(RetentionPolicy.RUNTIME)
@interface Annotation {

    // This annotation has two attributes.
    public String key();
    public String value();
}

// call Annotation for method
// and pass values for annotation
@Annotation(key = "GFG", value = "GeeksForGeeks")
public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object
        // for this myAnnotatedElement
        AnnotatedElement myAnnotatedElement
            = Test.class;

        System.out.println(
            "AnnotatedElement represented"
            + " by myAnnotatedElement: "
            + myAnnotatedElement.toString());

        // Check if there is any annotation
        // using isAnnotationPresent() method
        System.out.println(
            "If there is any annotation"
            + " in myAnnotatedElement: "
            + myAnnotatedElement
                  .isAnnotationPresent(
                      Annotation.class));
    }
}
```

**Output:**
> 由myAnnotatedElement表示的AnnotatedElement: class Test
> myAnnotatedElement中是否有注解: true

### 例 2：
```java
// Java program to demonstrate
// isAnnotationPresent() method

import java.util.*;
import java.lang.reflect.*;
import java.lang.annotation.*;

// Class with no annotations
public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object
        // for this myAnnotatedElement
        AnnotatedElement myAnnotatedElement
            = Test.class;

        System.out.println(
            "AnnotatedElement represented"
            + " by myAnnotatedElement: "
            + myAnnotatedElement.toString());

        // Get the annotation
        // using isAnnotationPresent() method
        System.out.println(
            "If there is any annotation"
            + " in myAnnotatedElement: "
            + myAnnotatedElement
                  .isAnnotationPresent(
                      Annotation.class));
    }
}
```

**Output:**
> 由myAnnotatedElement表示的AnnotatedElement: class Test
> myAnnotatedElement中是否有注解: false

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/lang/reflect/AnnotatedElement.html#isAnnotationPresent-java.lang.Class-](https://docs.oracle.com/javase/9/docs/api/java/lang/reflect/AnnotatedElement.html#isAnnotationPresent-java.lang.Class-)