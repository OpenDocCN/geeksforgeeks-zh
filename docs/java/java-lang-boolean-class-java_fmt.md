# Java 中的 Java.lang.Boolean 类

> 原文：[https://www.geeksforgeeks.org/java-lang-boolean-class-java/](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)

Java 在 `java.lang` 包中提供了一个包装类 `Boolean`。`Boolean` 类包装对象中的基本类型 `boolean` 的值。`Boolean` 类型的对象包含一个类型为 `boolean` 的字段。

此外，这个类提供了一些有用的方法，比如在处理布尔变量时，将布尔值转换为字符串，将字符串转换为布尔值。

## 创建布尔对象

`Boolean` 类为创建 `Boolean` 对象提供了两个构造函数。

*   下面的语句创建了一个包含值参数的 `Boolean` 对象。

```java
Boolean b = new Boolean(boolean value);
```

*   下面的语句创建一个 `Boolean` 对象，如果字符串参数不为空并且等于字符串“true”，则该对象包含值“true”，忽略大小写，否则创建值为“false”的 `Boolean` 对象。

```java
Boolean b = new Boolean(String s);
```

## 字段

*   **静态 `Boolean FALSE`**：图元值 `FALSE` 对应的 `Boolean` 对象。
*   **静态 `Boolean TRUE`**：与基元值 `TRUE` 对应的 `Boolean` 对象。
*   **静态 `Class`**：表示基元类型 `boolean` 型的 `Class` 对象。

## 方法

### 1. `static boolean parseBoolean(String s)`

此方法将字符串参数解析为 `boolean`。如果字符串参数不为 `null` 且等于（忽略大小写）字符串“true”，则返回的布尔值表示 `true`，否则返回 `false`。

```java
Syntax:
public static boolean parseBoolean(String s)
Parameters:
s - the String containing the boolean representation to be parsed
Returns:
the boolean represented by the string argument
```

```java
// Java program to demonstrate parseBoolean() method
public class Test
{
    public static void main(String[] args)
    {
        // parsing different Strings
        boolean b1 = Boolean.parseBoolean("True");
        boolean b2 = Boolean.parseBoolean("TruE");
        boolean b3 = Boolean.parseBoolean("False");
        boolean b4 = Boolean.parseBoolean("FALSE");
        boolean b5 = Boolean.parseBoolean("GeeksForGeeks");

        System.out.println(b1);
        System.out.println(b2);
        System.out.println(b3);
        System.out.println(b4);
        System.out.println(b5);
    }
}
```

输出：

```java
true
true
false
false
false
```

### 2. `boolean booleanValue()`

此方法返回此 `Boolean` 对象的 `boolean` 原始值。

```java
Syntax:
public boolean booleanValue()
Parameters:
NA
Returns:
the primitive boolean value of this object.
```

```java
// Java program to demonstrate booleanValue() method
public class Test
{
    public static void main(String[] args)
    {
        // creating different Boolean objects
        Boolean b1 = new Boolean("True");
        Boolean b2 = new Boolean("False");
        Boolean b3 = new Boolean("GeeksForGeeks");

        // getting primitive boolean value
        boolean b4 = b1.booleanValue();
        boolean b5 = b2.booleanValue();
        boolean b6 = b3.booleanValue();

        System.out.println(b4);
        System.out.println(b5);
        System.out.println(b6);
    }
}
```

输出：

```java
true
false
false
```

### 3. `static Boolean valueOf(boolean b)`

此方法返回表示指定 `boolean` 值的 `Boolean` 实例。如果指定的 `boolean` 值为 `true`，则返回 `Boolean.TRUE`；如果为 `false`，则返回 `Boolean.FALSE`。此方法的另一个变体将在下文讨论。

```java
Syntax:
public static Boolean valueOf(boolean b)
Parameters:
b - a boolean value.
Returns:
a Boolean object representing b.
```

```java
// Java program to demonstrate valueOf() method
public class Test
{
    public static void main(String[] args)
    {
        // creating boolean variable
        boolean b1 = true;
        boolean b2 = false;

        // getting Boolean objects from boolean variables
        Boolean b3 = Boolean.valueOf(b1);
        Boolean b4 = Boolean.valueOf(b2);

        System.out.println(b3);
        System.out.println(b4);
    }
}
```

输出：

```java
true
false
```

### 4. `static Boolean valueOf(String s)`

此方法返回一个由指定字符串 `s` 表示的值的 `Boolean`。如果字符串参数不为 `null` 且等于（忽略大小写）字符串“true”，则返回的 `Boolean` 表示 `true` 值。

# Java Boolean 类方法详解

## 5. `static String toString(boolean b)`

此方法返回一个表示指定布尔值的 `String` 对象。如果指定的布尔值为 `true`，则返回字符串 `"true"`；否则返回字符串 `"false"`。该方法的另一个变体将在下文讨论。

### Syntax
```java
public static String toString(boolean b)
```

### Parameters
- `b` - 要转换的布尔值

### Returns
- 指定布尔值的字符串表示形式

### 示例代码
```java
// Java program to demonstrate toString() method
public class Test
{
    public static void main(String[] args)
    {
        // creating boolean variable
        boolean b1 = true;
        boolean b2 = false;

        // getting String value of the primitives boolean
        String str1 = Boolean.toString(b1);
        String str2 = Boolean.toString(b2);

        System.out.println(str1);
        System.out.println(str2);
    }
}
```

### 输出
```
true
false
```

## 6. `String toString()`

此方法返回一个表示此 `Boolean` 对象值的 `String` 对象。如果此对象表示值 `true`，则返回一个等于 `"true"` 的字符串；否则返回字符串 `"false"`。

### Syntax
```java
public String toString()
```

### Parameters
- NA

### Returns
- 此对象的字符串表示形式

### Overrides
- `toString` in class `Object`

### 示例代码
```java
// Java program to demonstrate toString() method
public class Test
{
    public static void main(String[] args)
    {
        // creating different Boolean objects
        Boolean b1 = new Boolean("True");
        Boolean b2 = new Boolean("False");
        Boolean b3 = new Boolean("GeeksForGeeks");
        Boolean b4 = new Boolean(null);

        // getting String value of Boolean objects
        String str1 = b1.toString();
        String str2 = b2.toString();
        String str3 = b3.toString();
        String str4 = b4.toString();

        System.out.println(str1);
        System.out.println(str2);
        System.out.println(str3);
        System.out.println(str4);
    }
}
```

### 输出
```
true
false
false
false
```

## 7. `int hashCode()`

此方法返回此 `Boolean` 对象的哈希码。注意，`true` 的哈希码是 `1231`，`false` 的哈希码是 `1237`。要了解选择这些整数作为哈希码的原因，请参考[此处](http://stackoverflow.com/questions/3912303/boolean-hashcode)。

### Syntax
```java
public int hashCode()
```

### Parameters
- NA

### Returns
- 如果此对象表示 `true`，则返回整数 `1231`；如果此对象表示 `false`，则返回整数 `1237`

### Overrides
- `hashCode` in class `Object`

### 示例代码
```java
// Java program to demonstrate hashCode() method
public class Test
{
    public static void main(String[] args)
    {
        // creating different Boolean objects
        Boolean b1 = new Boolean("True");
        Boolean b2 = new Boolean("False");
        Boolean b3 = new Boolean("TRue");
        Boolean b4 = new Boolean(null);

        System.out.println(b1.hashCode());
        System.out.println(b2.hashCode());
        System.out.println(b3.hashCode());
        System.out.println(b4.hashCode());
    }
}
```

### 输出
```
1231
1237
1231
1237
```

## 8. `boolean equals(Object obj)`

此方法仅在参数不为 `null` 且是表示与此对象相同布尔值的 `Boolean` 对象时，返回 `true`。

### Syntax
```java
public boolean equals(Object obj)
```

### Parameters
- `obj` - 要比较的对象

### Returns
- 如果 `Boolean` 对象表示相同的值，则返回 `true`；否则返回 `false`

### Overrides
- `equals` in class `Object`

### 示例代码
```java
// Java program to demonstrate equals() method
public class Test
{
    public static void main(String[] args)
    {
        // creating different Boolean objects
        Boolean b1 = new Boolean("True");
        Boolean b2 = new Boolean("False");
        Boolean b3 = new Boolean("TrUe");
        Boolean b4 = new Boolean(null);

        // checking equality of Boolean objects
        System.out.println(b1.equals(b2));
        System.out.println(b2.equals(b4));
        System.out.println(b1.equals(b3));
        System.out.println(b1.equals(b4));
    }
}
```

### 输出
```
false
false
true
false
```

## 9. `int compareTo(Boolean b)`

此方法将此 `Boolean` 实例与传入的参数 `'b'` 进行“比较”。

### Syntax
```java
public int compareTo(Boolean b)
```

### Parameters
- `b` - 要比较的 `Boolean` 实例

### Returns
- 如果此对象表示的布尔值与参数相同，则返回零
- 如果此对象表示 `true` 而参数表示 `false`，则返回正值
- 如果此对象表示 `false` 而参数表示 `true`，则返回负值

### Throws
- `NullPointerException` - 如果参数为 `null`

### 示例代码
```java
// Java program to demonstrate compareTo() method
public class Test
{
    public static void main(String[] args)
    {
        // creating different Boolean objects
        Boolean b1 = new Boolean("True");
        Boolean b2 = new Boolean("False");
        Boolean b3 = new Boolean("TRue");
        Boolean b4 = new Boolean(null);

        //comparing b1,b2,b3,b4
        System.out.println(b1.compareTo(b2));
        System.out.println(b1.compareTo(b3));
        System.out.println(b2.compareTo(b1));
        System.out.println(b1.compareTo(b4));
        System.out.println(b2.compareTo(b4));

        // The following statement throws NullPointerException
        //  System.out.println(b1.compareTo(null));
    }
}
```

### 输出
```
-1
0
1
0
-1
```

## 10. `int compare(boolean x, boolean y)`

此方法用于“比较”原始布尔变量。

### Syntax
```java
public static int compare(boolean x, boolean y)
```

### Parameters
- `x` - 要比较的第一个布尔值
- `y` - 要比较的第二个布尔值

### Returns
- 如果 `x` 与 `y` 的布尔值相同，则返回零
- 如果 `x` 为 `true` 而 `y` 为 `false`，则返回正值
- 如果 `x` 为 `false` 而 `y` 为 `true`，则返回负值

### Throws
- `NullPointerException` - 如果参数为 `null`

### 示例代码
```java
// Java program to demonstrate compare() method
public class Test
{
    public static void main(String[] args)
    {
        // creating boolean variable
        boolean b1 = true;
        boolean b2 = false;
        boolean b3 = true;
        boolean b4 = false;

        //comparing b1,b2,b3,b4
        System.out.println(Boolean.compare(b1, b2));
        System.out.println(Boolean.compare(b1, b3));
        System.out.println(Boolean.compare(b2, b1));
        System.out.println(Boolean.compare(b2, b4));

        // The following statement throws NullPointerException
        //  System.out.println(Boolean.compare(b1, null));
    }
}
```

### 输出
```
1
0
-1
0
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。