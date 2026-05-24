# Java IO ObjectStreamField

> 原文：[https://www.geeksforgeeks.org/java-io-objectstreamfield/](https://www.geeksforgeeks.org/java-io-objectstreamfield/)

`java.io.ObjectStreamField` 类是来自 `Serializable` 接口的 `Serializable` 字段的描述。这个类是类的序列化描述符。`ObjectStreamField` 的数组用于维护类的可序列化字段。它包括类的名称和 `serialVersionUID`。

`ObjectStreamField` 的类声明如下：

```java
public class ObjectStreamField extends Object       // extends Keyword is used
public class ObjectStreamField implements Comparable<Object>   // implements Keyword is used
```

## Java IO ObjectStreamField 的构造函数

以下是 `ObjectStreamField` 类的两个构造函数：

| 编号 | 构造函数 | 描述 |
| :--- | :--- | :--- |
| 1 | `ObjectStreamField(String name, Class<?> type)` | 此构造函数创建一个可序列化字段。 |
| 2 | `ObjectStreamField(String name, Class<?> type, boolean non-shared)` | 此构造函数创建一个表示可序列化字段的 `ObjectStreamField`。 |

## Java IO ObjectStreamField 的方法

| 序列号 | 方法 | 方法类型 | 描述 |
| :--- | :--- | :--- | :--- |
| 1 | `compareTo(Object obj)` | `int` | 此方法将此字段与另一个 `ObjectStreamField` 进行比较。 |
| 2 | `getName()` | `String` | 此方法给出了字段的名称。 |
| 3 | `getType()` | `Class<?>` | 此方法给出了字段的类型。 |
| 4 | `getTypeString()` | `String` | 此方法返回字段类型的字符串表示形式。 |
| 5 | `getTypeCode()` | `char` | 此方法返回字段类型的字符编码。 |
| 6 | `isPrimitive()` | `boolean` | 如果字段具有基本类型，则返回 `true`。 |
| 7 | `getOffset()` | `int` | 此方法返回字段在对象中的偏移量。 |
| 8 | `isUnshared()` | `boolean` | 它返回一个布尔值，该值指示此 `ObjectStreamField` 实例表示的可序列化字段是否不共享。 |
| 9 | `setOffset(int offset)` | `protected void` | 此方法设置字段在对象内的偏移量。 |
| 10 | `toString()` | `String` | 它返回此字段的字符串表示形式。 |

### 示例

```java
// Java program to illustrate the working
// of the Java IO ObjectStreamField class
import java.io.ObjectStreamClass;
import java.util.Calendar;

public class ObjectStreamClassExample {
    public static void main(String[] args) {
        // creating a new object for the stream class for the Integers
        ObjectStreamClass abc = ObjectStreamClass.lookup(String.class);

        // getting the value field from ObjectStreamClass for the integers
        System.out.println("" + abc.getField("value"));

        // creating new object stream class for the Calendar
        ObjectStreamClass abc2 = ObjectStreamClass.lookup(Calendar.class);

        // get the Class instance for abc2
        System.out.println("" + abc2.getField("isTimeSet"));
    }
}
```

#### 输出：

```java
I value
Z isTimeSet
```

## Java IO ObjectStreamField 方法示例 (`compareTo(Object obj)`)

随后的插图解释了 `java.io.ObjectStreamField.compareTo()` 方法：

```java
// Java program to illustrate the working of the
// Java IO ObjectStreamField(compareTo(Object obj)) class
import java.io.*;

public class ObjectStreamField_ShowDemo {
    public static void main(String[] args) {
        // creating a new object stream class for The Integers
        ObjectStreamClass xyz = ObjectStreamClass.lookupAny(Integer.class);

        // getting the field value from Integer class
        ObjectStreamField field = xyz.getField("value");

        // creating a new object stream class for floats
        ObjectStreamClass xyz2 = ObjectStreamClass.lookupAny(Float.class);

        // getting the field value from Integer class
        ObjectStreamField field2 = xyz2.getField("value");

        // comparing with another field
        System.out.println("" + field.compareTo(field2));
    }
}
```

#### 输出：

```java
0
```