# Java 中的 `Field equals()` 方法示例

> 原文：[https://www.geeksforgeeks.org/field-equals-method-in-java-with-examples/](https://www.geeksforgeeks.org/field-equals-method-in-java-with-examples/)

`equals()` 方法用于比较两个 `Field` 对象。此方法比较两个字段对象，如果两个对象相等，则返回 `true`，否则返回 `false`。当且仅当这两个字段对象由同一类声明并且具有相同的名称和类型时，它们才被视为相等。这个方法在调试对象属性时非常有用，对象属性实际上是 Java 中一个类的字段。

## 语法

```java
public boolean equals(Object obj)
```

## 参数

该方法接受一个参数 `Object obj`，该参数是与该字段对象进行比较的参考对象。

## 返回值

如果两个对象相等，该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `equals()` 方法：

### 程序 1

```java
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get the array of Field objects
        Field[] fields
            = User.class.getDeclaredFields();
        Field fieldObj
            = User.class.getField("name");

        // print element of field array
        // and compare it with fieldObj
        for (int i = 0; i < fields.length; i++) {

            // compare the fields with each other
            boolean isEquals
                = fields[i].equals(fieldObj);
            if (isEquals) {
                System.out.println(
                    "Field -> ["
                    + fields[i] + "] and"
                    + " FieldObj -> ["
                    + fieldObj
                    + "] are equal.");
            }
            else {
                System.out.println(
                    "Field -> ["
                    + fields[i] + "] and"
                    + " FieldObj -> ["
                    + fieldObj
                    + "] are not equal.");
            }
        }
    }
}

// User class
class User {

    public String name;
    public int age;
}
```

**输出：**

> Field -> [public java.lang.String User.name] and FieldObj -> [public java.lang.String User.name] are equal.
> Field -> [public int User.age] and FieldObj -> [public java.lang.String User.name] are not equal.

### 程序 2

```java
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get the array of Field objects
        Field[] fields1
            = Class.class.getDeclaredFields();
        Field[] fields2
            = Class.class.getDeclaredFields();

        // print element of field array 1 and compare
        // it with fields array 2
        for (int i = 0; i < fields1.length; i++) {

            for (int j = 0; j < fields2.length; j++) {

                // compare the fields with each other
                boolean isEquals
                    = fields1[i].equals(fields2[j]);
                if (isEquals) {
                    System.out.println(
                        "Field -> ["
                        + fields1[i] + "] and"
                        + " FieldObj -> ["
                        + fields2[j]
                        + "] are equal.");
                }
                else {
                    System.out.println(
                        "Field -> ["
                        + fields1[i] + "] and"
                        + " FieldObj -> ["
                        + fields2[j]
                        + "] are not equal.");
                }
            }
        }
    }
}

// Object of Class which contains
// noOfStudents and studentNames
class Class {

    public int noOfStudents;
    public String[] studentNames;
}
```

**输出：**

> Field -> [public int Class.noOfStudents] and FieldObj -> [public int Class.noOfStudents] are equal.
> Field -> [public int Class.noOfStudents] and FieldObj -> [public java.lang.String[] Class.studentNames] are not equal.
> Field -> [public java.lang.String[] Class.studentNames] and FieldObj -> [public int Class.noOfStudents] are not equal.
> Field -> [public java.lang.String[] Class.studentNames] and FieldObj -> [public java.lang.String[] Class.studentNames] are equal.

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Field.html#equals(java.lang.Object)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Field.html#equals(java.lang.Object))