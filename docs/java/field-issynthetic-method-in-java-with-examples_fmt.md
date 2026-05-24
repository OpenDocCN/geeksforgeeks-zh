# Field 类的 isSynthetic() 方法，带有示例

> 原文: [https://www.geeksforgeeks.org/field-issynthetic-method-in-java-with-examples/](https://www.geeksforgeeks.org/field-issynthetic-method-in-java-with-examples/)

`java.lang.reflect.Field` 的 `isSynthetic()` 方法用于检查 `Field` 对象是否为合成字段。如果该字段是合成字段，则函数返回 `true`，否则返回 `false`。

**合成构造**: 合成构造是 Java 编译器为了内部目的而创建的类、字段和方法。

## 语法

```java
public boolean isSynthetic()
```

## 参数

此方法不接受任何参数。

## 返回值

当且仅当该字段是 Java 语言规范定义的合成字段时，该方法返回 `true`。

下面的程序说明了 `isSynthetic()` 方法：

### 程序 1

```java
// Java program to illustrate isSynthetic() method

import java.lang.reflect.Field;
import java.time.Month;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Get field object
        Field field
            = Numbers.class.getField("value");

        // check field is synthetic or not
        System.out.println(
            "The Field is isSynthetic: "
            + field.isSynthetic());
    }
}

// sample Numbers class
class Numbers {

    // static short value
    public static long value = 3114256;
}
```

**输出**

```java
The Field is isSynthetic: false
```

### 程序 2

```java
// Java program to illustrate isSynthetic() method

import java.lang.reflect.Field;
import java.time.DayOfWeek;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Get field object of Month class
        Field[] fields
            = DayOfWeek.class
                  .getDeclaredFields();

        for (int i = 0; i < fields.length; i++) {

            // print name of Fields
            System.out.println(
                "The Field "
                + fields[i].toString()
                + "\n is isSynthetic:"
                + fields[i].isSynthetic());
        }
    }
}
```

**输出**

> Field public static final java.time.DayOfWeek java.time.DayOfWeek.MONDAY
> is isSynthetic:false
> Field public static final java.time.DayOfWeek java.time.DayOfWeek.TUESDAY
> is isSynthetic:false
> Field public static final java.time.DayOfWeek java.time.DayOfWeek.WEDNESDAY
> is isSynthetic:false
> Field public static final java.time.DayOfWeek java.time.DayOfWeek.THURSDAY
> is isSynthetic:false
> Field public static final java.time.DayOfWeek java.time.DayOfWeek.FRIDAY
> is isSynthetic:false
> Field public static final java.time.DayOfWeek java.time.DayOfWeek.SATURDAY
> is isSynthetic:false
> Field public static final java.time.DayOfWeek java.time.DayOfWeek.SUNDAY
> is isSynthetic:false

**参考文献:** T2