# java.lang.reflect.Modifier 类

> 原文：[https://www.geeksforgeeks.org/java-lang-reflect-modifier-class-in-java/](https://www.geeksforgeeks.org/java-lang-reflect-modifier-class-in-java/)

`java.lang.reflect.Modifier` 类包含用于获取类、成员和方法访问修饰符信息的方法。修饰符被表示为 `int` 值，设置位位于不同的位置。`int` 值代表不同的修饰符。这些值取自 JVM 规范第 4.1、4.4、4.5 和 4.7 节中的表格。

## 类声明

```java
public class Modifier extends Object
```

## 字段

| **字段** | **描述** |
| --- | --- |
| `static int ABSTRACT` | 表示 `abstract` 修饰符的整数值。 |
| `static int FINAL` | 表示 `final` 修饰符的整数值。 |
| `static int INTERFACE` | 表示 `interface` 修饰符的整数值。 |
| `static int NATIVE` | 表示 `native` 修饰符的整数值。 |
| `static int PRIVATE` | 表示 `private` 修饰符的整数值。 |
| `static int PROTECTED` | 表示 `protected` 修饰符的整数值。 |
| `static int PUBLIC` | 表示 `public` 修饰符的整数值。 |
| `static int STATIC` | 表示 `static` 修饰符的整数值。 |
| `static int STRICT` | 表示 `strictfp` 修饰符的整数值。 |
| `static int SYNCHRONIZED` | 表示 `synchronized` 修饰符的整数值。 |
| `static int TRANSIENT` | 表示 `transient` 修饰符的整数值。 |
| `static int VOLATILE` | 表示 `volatile` 修饰符的整数值。 |

## 构造方法

```java
protected Modifier()
```
默认构造方法。

## 方法

| **方法** | **描述** |
| --- | --- |
| `static int classModifiers()` | 返回一个 `int` 值，该值是对可应用于类的源语言修饰符进行“或”操作后的结果。 |
| `static int constructorModifiers()` | 返回一个 `int` 值，该值是对可应用于构造方法的源语言修饰符进行“或”操作后的结果。 |
| `static int fieldModifiers()` | 返回一个 `int` 值，该值是对可应用于字段的源语言修饰符进行“或”操作后的结果。 |
| `static int interfaceModifiers()` | 返回一个 `int` 值，该值是对可应用于接口的源语言修饰符进行“或”操作后的结果。 |
| `static boolean isAbstract(int mod)` | 如果整型参数包含 `abstract` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isFinal(int mod)` | 如果整型参数包含 `final` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isInterface(int mod)` | 如果整型参数包含 `interface` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isNative(int mod)` | 如果整型参数包含 `native` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isPrivate(int mod)` | 如果整型参数包含 `private` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isProtected(int mod)` | 如果整型参数包含 `protected` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isPublic(int mod)` | 如果整型参数包含 `public` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isStatic(int mod)` | 如果整型参数包含 `static` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isSynchronized(int mod)` | 如果整型参数包含 `synchronized` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isTransient(int mod)` | 如果整型参数包含 `transient` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static boolean isVolatile(int mod)` | 如果整型参数包含 `volatile` 修饰符，则返回 `true`；否则返回 `false`。 |
| `static int methodModifiers()` | 返回一个 `int` 值，该值是对可应用于方法的源语言修饰符进行“或”操作后的结果。 |
| `static int parameterModifiers()` | 返回一个 `int` 值，该值是对可应用于参数的源语言修饰符进行“或”操作后的结果。 |
| `static String toString(int mod)` | 返回描述指定修饰符中访问修饰符标志的字符串。 |

### `static int classModifiers()`

此方法在对可应用于类的访问修饰符执行“或”操作后返回一个整数值。

返回类型：`int`

```java
// Implementation of classModifiers() Method
import java.lang.reflect.Modifier;

public class GFG {
    public static void main(String[] args)
    {
        System.out.println(Modifier.classModifiers());
        System.out.println(
            Modifier.toString(Modifier.classModifiers()));
    }
}
```

**输出**

```
public protected private abstract static final strictfp
```

### `static int constructorModifiers()`

对可应用于构造函数的访问修饰符执行“或”操作后，返回一个整数值。

返回类型：`int`

```java
// Implementation of constructorModifiers() Method
import java.lang.reflect.Modifier;

public class GFG {
    public static void main(String[] args)
    {
        System.out.println(Modifier.constructorModifiers());
        System.out.println(Modifier.toString(
            Modifier.constructorModifiers()));
    }
}
```

**输出**

```
public protected private
```

### `static int fieldModifiers()`

对可应用于字段的访问修饰符执行 OR 操作后返回一个 `int` 值。

返回类型：`int`

```java
// Implementation of fieldModifiers() Method
import java.lang.reflect.Modifier;

public class GFG {
    public static void main(String[] args)
    {
        System.out.println(Modifier.fieldModifiers());
        System.out.println(Modifier.toString(
            Modifier.fieldModifiers()));
    }
}
```

**输出**

```
public protected private static final transient volatile
```