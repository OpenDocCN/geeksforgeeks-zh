# Method类：Java中的getParameterAnnotations()方法

> 原文：[https://www.geeksforgeeks.org/method-class-getparameterannotations-method-in-java/](https://www.geeksforgeeks.org/method-class-getparameterannotations-method-in-java/)

`Method`类的`getParameterAnnotations()`方法返回一个二维`Annotation`数组，代表方法对象的参数注释。如果方法不包含参数，将返回一个空数组。如果该方法包含一个或多个参数，则将返回一个二维注释数组。对于没有注释的参数，此二维数组的嵌套数组将为空。

在编译时，强制和合成参数被添加到数组中。强制参数是在源中隐式声明的参数，合成参数是在源中既不隐式也不显式声明的参数。

此方法返回的注释对象是可序列化的。此方法返回的数组可以很容易地修改。

## 语法

```java
public Annotation[][] getParameterAnnotations()
```

## 返回值

该方法返回一个二维注释数组，表示方法对象的形式参数和隐式参数的注释。

## 示例1

对作为输入给定的特定方法使用`getParameterAnnotations()`。

该程序包含一个方法名`setManyValues()`，其中包含参数注释。所以这个程序将获取`setManyValues()`方法包含的所有参数注释。

```java
// Java program to demonstrate how to
// apply getParameterAnnotations() method
// of Method Class.

import java.lang.annotation.Annotation;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.reflect.Method;

public class GFG {

// Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = GFG.class;

// create method object of setManyValues
            Method setManyValueObject = null;

Method[] methods = classobj.getMethods();

for (Method m : methods) {
                if (m.getName().equals("setManyValues"))
                    setManyValueObject = m;
            }

// get Annotation of parameter
            Annotation[][] Arrayannotations = setManyValueObject
                                              .getParameterAnnotations();

System.out.println("Method Name: "
                           + setManyValueObject.getName());

// print parameter annotation
            for (Annotation[] annotationRow : Arrayannotations) {
                for (Annotation annotation : annotationRow) {
                    AnnotationDemo anndemo = (AnnotationDemo)annotation;
                    System.out.println("key of annotation: "
                                       + anndemo.key());
                    System.out.println("value of annotation: "
                                       + anndemo.value());
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

// method name setManyValues
    public void
        setManyValues(@AnnotationDemo(key = "methodParameter1",
                                      value = "Some value")
                      String parameter1)
    {
        System.out.println("setManyValues");
    }
}

// create a custom Annotation to apply on method
@Retention(RetentionPolicy.RUNTIME)
@interface AnnotationDemo {

// This annotation has two attributes.
    public String key();

public String value();
}
```

**输出：**

```java
Method Name: setManyValues
key of annotation: methodParameter1
value of annotation: Some value
```

## 示例2

如果方法包含`ParameterAnnotations`，则对`GFG`类的方法使用`getParameterAnnotations()`。

```java
// Java program to demonstrate how to
// apply getParameterAnnotations() method
// of Method Class.

import java.lang.annotation.Annotation;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.reflect.Method;

public class GFG {

// Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = GFG.class;

// create list of method objects
            Method[] methods = classobj.getMethods();

for (Method m : methods) {

// print details for only getValues
                // and setValue method
                // so filter list of methods
                if (m.getName().equals("getValues")
                    || m.getName().equals("setValue")) {

// get Annotations of parameter
                    Annotation[][] Arrayannotations
                        = m
                          .getParameterAnnotations();

System.out.println("Method Name: "
                                       + m.getName());

// print parameter annotation
                    printAnnotation(Arrayannotations);
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

// method name setValue with
    // no annotations at parameter
    public void setValue()
    {
        System.out.println("setValue");
    }

// method name getValues with annotations at the parameter
    public String
        getValues(@AnnotationDemo(field1 = "GFG",
                                  field2 = "Works",
                                  field3 = "fine",
                                  field4 = "Hurray!!")
                  String value)
    {
        System.out.println("setManyValues");
        return value;
    }

public static void
        printAnnotation(Annotation[][] Arrayannotations)
    {
        System.out.println("Annotation length: "
                           + Arrayannotations.length);

// print parameter annotation
        for (Annotation[] annotationRow : Arrayannotations) {
            for (Annotation annotation : annotationRow) {

AnnotationDemo anndemo = (AnnotationDemo)annotation;
                System.out.println("field1 of annotation: "
                                   + anndemo.field1());
                System.out.println("field2 of annotation: "
                                   + anndemo.field2());
                System.out.println("field3 of annotation: "
                                   + anndemo.field3());
                System.out.println("field4 of annotation: "
                                   + anndemo.field4());
            }
        }
    }
}

// create a custom Annotation to apply on method
@Retention(RetentionPolicy.RUNTIME)
@interface AnnotationDemo {

// This annotation has many attributes.
    public String field1();
    public String field2();
    public String field3();
    public String field4();
}
```

**输出：**

```java
Method Name: getValues
Annotation length: 1
field1 of annotation: GFG
field2 of annotation: Works
field3 of annotation: fine
field4 of annotation: Hurray!!
Method Name: setValue
Annotation length: 0
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getParameterAnnotations--](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getParameterAnnotations--)