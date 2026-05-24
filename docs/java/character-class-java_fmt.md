# Java 中的 `Character` 类

> 原文：[`https://www.geeksforgeeks.org/character-class-java/`](https://www.geeksforgeeks.org/character-class-java/)

Java 在 `java.lang` 包中提供了一个包装类 `Character`。字符类型的对象包含一个类型为 `char` 的字段。

## Creating a Character object

```java
Character ch = new Character('a');
```

上面的语句创建了一个 `Character` 对象，它包含一个 `char` 类型的值。`Character` 类中只有一个构造函数，需要 `char` [数据类型](https://www.geeksforgeeks.org/data-types-in-java/)的参数。

- 如果我们将一个基本类型 `char` 传递给一个需要对象的方法，编译器会自动将该 `char` 转换为一个 `Character` 对象。该功能称为[自动装箱和取消装箱](https://docs.oracle.com/javase/tutorial/java/data/autoboxing.html)。
- **注意**：`Character` 类像 `String` 类一样是不可变的，即一旦创建了它的对象，它**就不能**被更改。

## `Character` 类中的方法

### `boolean isLetter(char ch)`

此方法用于确定指定的 `char` 值（`ch`）是否为字母。如果 `ch` 是字母（`[A-Z]`, `[a-z]`），该方法将返回 `true`，否则返回 `false`。除了字符，我们也可以传递 `ASCII` 值作为参数，因为在 Java 中 `char` 到 `int` 是隐式类型转换的。

```java
Syntax:
boolean isLetter(char ch)
Parameters:
ch - a primitive character
Returns:
returns true if ch is a alphabet, otherwise return false
```

```java
// Java program to demonstrate isLetter() method
public class Test
{
    public static void main(String[] args)
    {
        System.out.println(Character.isLetter('A'));
        System.out.println(Character.isLetter('0'));
    }
}
```

输出：

```java
true
false
```

### `boolean isDigit(char ch)`

此方法用于确定指定的 `char` 值（`ch`）是否为数字。这里我们也可以传递 `ASCII` 值作为参数。

```java
Syntax:
boolean isDigit(char ch)
Parameters:
ch - a primitive character
Returns:
returns true if ch is a digit, otherwise return false
```

```java
// Java program to demonstrate isDigit() method
public class Test
{
    public static void main(String[] args)
    {
        // print false as A is character
        System.out.println(Character.isDigit('A'));
        System.out.println(Character.isDigit('0'));
    }
}
```

输出：

```java
false
true
```

### `boolean isWhitespace(char ch)`

它确定指定的 `char` 值（`ch`）是否为空白字符。空白字符包括空格、制表符或换行符。

```java
Syntax:
boolean isWhitespace(char ch)
Parameters:
ch - a primitive character
Returns:
returns true if ch is a whitespace.
otherwise return false
```

```java
// Java program to demonstrate isWhitespace() method
public class Test
{
    public static void main(String[] args)
    {
        System.out.println(Character.isWhitespace('A'));
        System.out.println(Character.isWhitespace(' '));
        System.out.println(Character.isWhitespace('\n'));
        System.out.println(Character.isWhitespace('\t'));
        //ASCII value of tab
        System.out.println(Character.isWhitespace(9));
        System.out.println(Character.isWhitespace('9'));
    }
}
```

输出：

```java
false
true
true
true
true
false
```

### `boolean isUpperCase(char ch)`

它确定指定的 `char` 值（`ch`）是否为大写字母。

```java
Syntax:
boolean isUpperCase(char ch)
```

```java
// Java program to demonstrate isUpperCase() method
public class Test
{
  public static void main(String[] args)
  {
    System.out.println(Character.isUpperCase('A'));
    System.out.println(Character.isUpperCase('a'));
    System.out.println(Character.isUpperCase(65));
  }
}
```

输出：

```java
true
false
true
```

### `boolean isLowerCase(char ch)`

它确定指定的 `char` 值（`ch`）是否为小写字母。

```java
Syntax:
boolean isLowerCase(char ch)
```

```java
// Java program to demonstrate isLowerCase() method
public class Test
{
  public static void main(String[] args)
  {
    System.out.println(Character.isLowerCase('A'));
    System.out.println(Character.isLowerCase('a'));
    System.out.println(Character.isLowerCase(97));
   }
}
```

输出：

```java
false
true
true
```

### `char toUpperCase(char ch)`

它返回指定 `char` 值（`ch`）的大写形式。如果传递的是 `ASCII` 值，则将返回其对应大写字母的 `ASCII` 值。

```java
Syntax:
char toUpperCase(char ch)
Parameters:
ch - a primitive character
Returns:
returns the uppercase form of the specified char value.
```

```java
// Java program to demonstrate toUpperCase() method
public class Test
{
   public static void main(String[] args)
   {
     System.out.println(Character.toUpperCase('a'));
     System.out.println(Character.toUpperCase(97));
     System.out.println(Character.toUpperCase(48));
   }
}
```

输出：

```java
A
```

### `char toLowerCase(char ch)`

它返回指定 `char` 值（`ch`）的小写形式。

```java
Syntax:
char toLowerCase(char ch)
Parameters:
ch - a primitive character
Returns:
returns the lowercase form of the specified char value.
```

```java
// Java program to demonstrate toLowerCase() method
public class Test
{
   public static void main(String[] args)
   {
     System.out.println(Character.toLowerCase('A'));
     System.out.println(Character.toLowerCase(65));
     System.out.println(Character.toLowerCase(48));
   }
}
```

输出：

```java
a
```

### `String toString(char ch)`

它返回一个表示指定字符值（`ch`）的 `String` 类对象，即一个单字符字符串。这里我们**不能**传递 `ASCII` 值。

```java
Syntax:
String toString(char ch)
Parameters:
ch - a primitive character
Returns:
returns a String object.
```

```java
// Java program to demonstrate toString() method
public class Test
{
   public static void main(String[] args)
   {
    System.out.println(Character.toString('x'));
    System.out.println(Character.toString('Y'));
   }
}
```

输出：

```java
x
Y
```

9.  `static int charCount(int codePoint)`: 此方法确定表示指定字符(Unicode 代码点)所需的字符值数量。
10. `char charValue()`: 这个方法返回这个 `Character` 对象的值。
11. `static int codePointAt(char[] a, int index)`: 此方法返回 `char` 数组给定索引处的代码点。
12. `static int codePointAt(char[] a, int index, int limit)`: 此方法返回 `char` 数组给定索引处的代码点，这里只能使用索引小于 `limit` 的数组元素。
13. `static int codePointAt(CharSequence seq, int index)`: 此方法返回 `CharSequence` 给定索引处的代码点。
14. `static int codePointBefore(char[] a, int index)`: 此方法返回 `char` 数组给定索引之前的代码点。
15. `static int codePointBefore(char[] a, int index, int start)`: 此方法返回 `char` 数组给定索引之前的代码点，其中只能使用索引大于等于 `start` 的数组元素。
16. `static int codePointBefore(CharSequence seq, int index)`: 此方法返回 `CharSequence` 给定索引之前的代码点。
17. `static int codePointCount(char[] a, int offset, int count)`: 此方法返回 `char` 数组参数的子数组中的 Unicode 码点数。
18. `static int codePointCount(CharSequence seq, int beginIndex, int endIndex)`: 此方法返回指定字符序列文本范围内的 Unicode 码点数。
19. `static int codePointOf(String name)`: 此方法返回给定 Unicode 字符名称指定的 Unicode 字符的代码点值。
20. `static int compare(char x, char y)`: 此方法对两个 `char` 值进行数值比较。
21. `int compareTo(Character other)`: 该方法对两个 `Character` 对象进行数值比较。
22. `static int digit(char ch, int radix)`: 该方法返回指定基数下字符 `ch` 的数值。
23. `static int digit(int codePoint, int radix)`: 此方法返回指定基数内指定字符(Unicode 码点)的数值。
24. `boolean equals(Object obj)`: 此方法将此对象与指定对象进行比较。
25. `static char forDigit(int digit, int radix)`: 此方法确定指定基数中特定数字的字符表示。
26. `static byte getDirectionality(char ch)`: 此方法返回给定字符的 Unicode directionality 属性。
27. `static byte getDirectionality(int codePoint)`: 此方法返回给定字符(Unicode 代码点)的 Unicode directionality 属性。
28. `static String getName(int codePoint)`: 此方法返回指定字符 `codePoint` 的 Unicode 名称，如果代码点未赋值则返回 `null`。
29. `static int getNumericValue(char ch)`: 此方法返回指定 Unicode 字符表示的 `int` 值。
30. `static int getNumericValue(int codePoint)`: 此方法返回指定字符(Unicode 代码点)表示的 `int` 值。
31. `static int getType(char ch)`: 这个方法返回一个值，表示一个角色的一般类别。
32. `static int getType(int codePoint)`: 这个方法返回一个值，表示一个角色的一般类别。
33. `int hashCode()`: 这个方法返回这个字符的 hash 码；等于调用 `charValue()` 的结果。
34. `static int hashCode(char value)`: 这个方法返回一个 `char` 值的 hash 码；与 `Character.hashCode()` 兼容。
35. `static char highSurrogate(int codePoint)`: 此方法返回表示 UTF-16 编码中指定补充字符(Unicode 代码点)的代理项对的前导代理项(高代理项代码单元)。
36. `static boolean isAlphabetic(int codePoint)`: 此方法确定指定的字符(Unicode 代码点)是否为字母表。
37. `static boolean isBmpCodePoint(int codePoint)`: 此方法确定指定字符(Unicode 码点)是否在基本多语言平面(BMP)中。
38. `static boolean isDefined(char ch)`: 这个方法确定一个字符是否用 Unicode 定义。
39. `static boolean isDefined(int codePoint)`: 此方法确定字符(Unicode 代码点)是否定义在 Unicode 中。
40. `static boolean isHighSurrogate(char ch)`: 此方法确定给定的 `char` 值是否为 Unicode 高代理代码单元(也称为前导代理代码单元)。
41. `static boolean isIdentifierIgnorable(char ch)`: 此方法确定在 Java 标识符或 Unicode 标识符中指定的字符应该被视为可忽略字符。
42. `static boolean isIdentifierIgnorable(int codePoint)`: 这个方法决定了指定的字符(Unicode 代码点)应该被视为 Java 标识符中的可忽略字符还是 Unicode 标识符中的可忽略字符。
43. `static boolean isIdeographic(int codePoint)`: 此方法确定指定字符(Unicode 代码点)是否为 Unicode 标准定义的 CJKV(中文、日文、韩文和越南语)表意字符。
44. `static boolean isISOControl(char ch)`: 此方法确定指定字符是否为 ISO 控制字符。
45. `static boolean isISOControl(int codePoint)`: 此方法确定引用的字符(Unicode 代码点)是否为 ISO 控制字符。
46. `static boolean isJavaIdentifierPart(char ch)`: 此方法确定指定的字符是否可能是 Java 标识符的一部分，而不是第一个字符。
47. `static boolean isJavaIdentifierPart(int codePoint)`: 此方法确定字符(Unicode 代码点)是否可能是 Java 标识符的一部分，而不是第一个字符。
48. `static boolean isJavaIdentifierStart(char ch)`: 此方法确定指定的字符是否允许作为 Java 标识符中的第一个字符。
49. `static boolean isJavaIdentifierStart(int codePoint)`: 此方法确定字符(Unicode 代码点)是否允许作为 Java 标识符中的第一个字符。
50. `static boolean isLowSurrogate(char ch)`: 此方法确定给定的 `char` 值是否为 Unicode 低代理代码单元(也称为尾随代理代码单元)。
51. `static boolean isLetterOrDigit(char ch)`: 这个方法确定指定的字符是字母还是数字。
52. `static boolean isLetterOrDigit(int codePoint)`: 此方法确定指定字符(Unicode 代码点)是字母还是数字。
53. `static boolean isMirrored(char ch)`: 此方法决定字符是否按照 Unicode 规范镜像。
54. `static boolean isMirrored(int codePoint)`: 此方法确定指定字符(Unicode 码点)是否按照 Unicode 规范镜像。
55. `static boolean isSpaceChar(char ch)`: 此方法确定指定字符是否为 Unicode 空格字符。
56. `static boolean isSpaceChar(int codePoint)`: 此方法确定指定字符(Unicode 代码点)是否为 Unicode 空格字符。
57. `static boolean isSupplementaryCodePoint(int codePoint)`: 此方法判断指定字符(Unicode 码点)是否在补充字符范围内。
58. `static boolean isSurrogate(char ch)`: 此方法确定给定的 `char` 值是否是 Unicode 代理代码单元。
59. `static boolean isSurrogatePair(char high, char low)`: 此方法确定指定的字符值对是否是有效的 Unicode 代理项对。
60. `static boolean isTitleCase(char ch)`: 此方法判断指定字符是否为 TitleCase 字符。
61. `static boolean isTitleCase(int codePoint)`: 此方法确定指定字符(Unicode 代码点)是否为 TitleCase 字符。
62. `static boolean isUnicodeIdentifierPart(char ch)`: 此方法确定指定字符是否可能是 Unicode 标识符的一部分，而不是第一个字符。
63. `static boolean isUnicodeIdentifierPart(int codePoint)`: 此方法确定指定字符(Unicode 代码点)是否可能是 Unicode 标识符的一部分，而不是第一个字符。
64. `static boolean isUnicodeIdentifierStart(char ch)`: 此方法确定指定字符是否允许作为 Unicode 标识符中的第一个字符。
65. `static boolean isUnicodeIdentifierStart(int codePoint)`: 此方法确定指定字符(Unicode 代码点)是否允许作为 Unicode 标识符中的第一个字符。
66. `static boolean isValidCodePoint(int codePoint)`: 此方法确定指定的代码点是否为有效的 Unicode 代码点值。
67. `static char lowSurrogate(int codePoint)`: 此方法返回表示 UTF-16 编码中指定补充字符(Unicode 代码点)的代理项对的尾随代理项(低代理项代码单位)。
68. `static int offsetByCodePoints(char[] a, int start, int count, int index, int codePointOffset)`: 此方法返回给定 `char` 子数组内的索引，该索引从给定索引偏移了 `codePointOffset` 代码点。
69. `static int offsetByCodePoints(CharSequence seq, int index, int codePointOffset)`: 此方法返回给定 `CharSequence` 内的索引，该索引从给定索引偏移了 `codePointOffset` 代码点。

`org/character-offsetbycodepoints-method-in-java/)`：此方法返回给定字符序列内的索引，该索引从给定索引偏移了`codePointOffset`代码点。
70. `static char reverseBytes(char ch)`：此方法返回通过反转指定`char`值中字节的顺序获得的值。
71. `static char[] toChars(int codePoint)`：此方法将指定字符(Unicode 代码点)转换为存储在`char`数组中的UTF-16表示形式。
72. `static int toChars(int codePoint, char[] dst, int dstIndex)`：此方法将指定字符(Unicode 代码点)转换为其UTF-16表示形式。
73. `static int toCodePoint(char high, char low)`：此方法将指定的代理项对转换为其补充代码点值。
74. `static char toTitleCase(char ch)`：这个方法使用来自UnicodeData文件的大小写映射信息，将字符参数转换为TitleCase。
75. `static int toTitleCase(int codePoint)`：此方法使用Unicode数据文件中的大小写映射信息将字符(Unicode 代码点)参数转换为TitleCase。
76. `static Character valueOf(char c)`：此方法返回一个表示指定字符值的`Character`实例。

**转义序列:**
以反斜杠(`\`)开头的字符是转义序列，对编译器有特殊意义。下表显示了Java转义序列：

| 换码顺序 | 描述 |
| :--- | :--- |
| `\t` | 此时在文本中插入一个制表符。 |
| `\b` | 此时在文本中插入退格。 |
| `\n` | 此时在文本中插入一个换行符。 |
| `\r` | 此时在文本中插入回车。 |
| `\f` | 此时在文本中插入一个formfeed。 |
| `\'` | 此时在文本中插入一个单引号字符。 |
| `\"` | 此时在文本中插入一个双引号字符。 |
| `\\` | 此时在文本中插入一个反斜杠字符。 |

当在`print`语句中遇到转义序列时，编译器会相应地解释它。例如，如果要在引号内加上引号，必须在内部引号上使用转义序列“\”。打印句子

```java
She said "Hello!" to me.
```

你会写

```java
System.out.println("She said \"Hello!\" to me.");
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢GeeksforGeeks并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。