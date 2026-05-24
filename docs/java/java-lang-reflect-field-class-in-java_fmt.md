# java 中的 java.lang.reflect.Field 类

> 原文：[https://www.geeksforgeeks.org/java-lang-reflect-field-class-in-Java/](https://www.geeksforgeeks.org/java-lang-reflect-field-class-in-java/)

软件自我分析的能力被称为反射。这由类中的 [`java.lang.reflect`](https://www.geeksforgeeks.org/tag/java-lang-reflect-package/) 包和元素提供。字段的作用与整个反射机制相同，在运行时而不是编译时分析软件组件并动态描述其功能。像许多其他语言一样，Java 是静态类型的。反射机制允许人们在某种程度上绕过它，并引入一些更动态的特性，比如，按名称检索字段的值。`java.lang.reflect` 包包括几个接口。特别感兴趣的是 `Member`，它定义了允许获取关于字段、构造函数或类方法的信息的方法。这个包中还有十个类，即 `AccessibleObject`、`Array`、`Constructor`、`Executable`、`Field`、`Method`、`Modifier`、`Parameter`、`Proxy`、`ReflectPermission`。

下面的应用程序演示了 Java 反射的简单用法。它打印类 [`java.awt.Dimension`](https://www.geeksforgeeks.org/java-awt-dimension-class/) 的字段。程序以 `Class` 的 `forName()` 方法开始，获取 `java.awt.Dimension` 的一个类对象，一旦得到这个类对象，就用 `getFields()` 来分析这个类对象。它们返回一个提供对象信息的 `Field` 对象数组。

| **方法** | **描述** |
| --- | --- |
| `equals(Object obj)` | 此方法将此字段与指定的对象进行比较。 |
| `getAnnotatedType()` | 此方法返回一个 `AnnotatedType` 对象，该对象表示使用类型来指定此字段所表示的字段的声明类型 |
| `getAnnotation(Class annotationClass)` | 如果存在指定类型的注释，则此方法返回此元素的注释，否则为 `null`。 |
| `getAnnotationsByType(Class annotationClass)` | 此方法返回与此元素关联的注释 |
| `getBoolean(Object obj)` | 此方法获取静态或实例 `boolean` 字段的值 |
| `getByte(Object obj)` | 此方法获取静态或实例 `byte` 字段的值 |
| `getChar(Object obj)` | 此方法获取 `char` 类型的静态或实例字段的值，或者通过扩展转换可转换为 `char` 类型的另一个基元类型的值 |
| `getDeclaredAnnotations()` | 此方法返回直接出现在此元素上的注释 |
| `getDeclaringClass()` | 此方法返回表示类或接口的 `Class` 对象，该类或接口声明由该 `Field` 对象表示的字段 |
| `getDouble(Object obj)` | 此方法获取 `double` 类型的静态字段或实例字段的值，或者通过扩展转换可转换为 `double` 类型的另一个基元类型的值 |
| `getFloat(Object obj)` | 此方法获取类型为 `float` 的静态字段或实例字段的值，或者通过扩展转换可转换为类型 `float` 的另一基本类型的值 |
| `getGenericType()` | 此方法返回一个 `Type` 对象，该对象表示此 `Field` 对象所表示的字段的声明类型 |
| `getInt(Object obj)` | 此方法返回一个 `Type` 对象，该对象表示此 `Field` 对象所表示的字段的声明类型 |
| `getLong(Object obj)` | 此方法获取 `long` 类型的静态或实例字段的值，或者通过扩展转换可转换为 `long` 类型的另一个基元类型的值 |
| `getModifiers()` | 此方法以整数形式返回此 `Field` 对象表示的字段的 Java 语言修饰符 |
| `getName()` | 此方法返回由该 `Field` 对象表示的字段的名称 |
| `getShort(Object obj)` | 此方法获取 `short` 类型的静态或实例字段的值，或者通过扩展转换可转换为 `short` 类型的另一个基元类型的值 |
| `hashCode()` | 此方法返回该字段的哈希码。 |
| `isEnumConstant()` | 如果此字段表示枚举类型的元素，则此方法返回 `true` 否则返回 `false` |
| `isSynthetic()` | 如果此字段是合成字段，则此方法返回 `true` 否则返回 `false` |
| `setBoolean(Object obj, boolean z)` | 此方法将字段的值设置为指定对象上的布尔值 |
| `setByte(Object obj, byte b)` | 此方法将字段的值设置为指定对象上的字节 |
| `setChar(Object obj, char c)` | 此方法将字段的值设置为指定对象上的字符 |
| `setDouble(Object obj, double d)` | 此方法将字段的值设置为指定对象上的双精度值 |
| `setFloat(Object obj, float f)` | 此方法将字段的值设置为指定对象上的浮点数 |
| `setInt(Object obj, int i)` | 此方法将指定对象上的字段值设置为 `int` |
| `setLong(Object obj, long l)` | 此方法将指定对象上的字段值设置为 `long` |
| `setShort(Object obj, short s)` | 此方法将指定对象上的字段值设置为短整型 |
| `toGenericString()` | 此方法返回描述此字段的字符串，包括其泛型类型 |
| `toString()` | 此方法返回描述此字段的字符串 |

## 示例1

```java
import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args) throws Exception {
        // Create the User class object
        User user = new User();

        // Get the all field objects of User class
        Field[] fields = User.class.getFields();

        for (int i = 0; i < fields.length; i++) {
            // get value of the fields
            Object value = fields[i].get(user);

            // print result
            System.out.println("Value of Field "
                               + fields[i].getName()
                               + " is " + value);
        }
    }
}

// sample User class
class User {
    public static String name = "Dipsundar";

    public static String getName() {
        return name;
    }

    public static void setName(String name) {
        User.name = name;
    }
}
```

**输出**

```java
Value of Field name is Dipsundar
```

## 示例2

```java
import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args) throws Exception {
        // Create the User class object
        User user = new User();

        // Get the all field objects of User class
        Field[] fields = User.class.getFields();

        for (int i = 0; i < fields.length; i++) {
            // get value of the fields
            Object value = fields[i].get(user);

            // print result
            System.out.println("Value of Field "
                               + fields[i].getName()
                               + " is " + value);
        }
    }
}

// sample User class
class User {
    public static boolean booleanValue = false;

    public static boolean getBooleanValue() {
        return booleanValue;
    }

    public static void setBooleanValue(boolean booleanValue) {
        User.booleanValue = booleanValue;
    }
}
```

**输出**

```java
Value of Field booleanValue is false
```