# Java 中的 Character.UnicodeBlock 类

> 原文：[https://www.geeksforgeeks.org/java-lang-character-unicodeblock-class-java/](https://www.geeksforgeeks.org/java-lang-character-unicodeblock-class-java/)

`Character.UnicodeBlock` 类代表 Unicode（使用十六进制值表示字符的标准——16 位）规范的特定 **字符块**。字符块定义用于特定目的的字符。

## 声明

```java
public static final class Character.UnicodeBlock
   extends Character.Subset
```

## Character.UnicodeBlock 类的方法

### `forName()`

`Character.UnicodeBlock.forName()` 返回 Unicode 块的名称，由 Unicode 标准确定。根据 Unicode 标准，该方法接受作为规范块的参数。

**语法：**

```java
public static final Character.UnicodeBlock forName(String block)
```

**参数：**
- `block`：Unicode 块的名称。

**返回：**
- Unicode 块的实例。

**异常：**
- `IllegalArgumentException`
- `NullPointerException`

### `of(char ch)`

`Character.Subset.of(char ch)` 返回具有参数字符的 Unicode 块，如果该字符不是任何已定义的 Unicode 块的一部分，则返回 `null`。

**语法：**

```java
public static Character.UnicodeBlock of(char ch)
```

**参数：**
- `ch`：要查找的字符。

**返回：**
- 返回 Unicode 块或 `null`。

**异常：**
- `IllegalArgumentException`

### `of(int UCPoint)`

`Character.Subset.of(int UCPoint)` 返回具有参数 Unicode 点的对象，如果该字符不是任何已定义 Unicode 块的一部分，则返回 `null`。

**语法：**

```java
public final String toString()
```

**参数：**
- ---

**返回：**
- 返回具有参数 Unicode 点的对象或 `null`。

**异常：**
- `IllegalArgumentException`

## 代码示例

```java
// Java Program illustrating the use of
// Character.UnicodeBlock class Methods.
import java.lang.*;

public class CharacterSubsetDemo {
    public static void main(String[] args) {
        // Use of forName() :
        // returns Unicode Blocks, as per Unicode Standards
        System.out.println("Using UnicodeBlock.forName() : ");
        System.out.println(Character.UnicodeBlock.forName("OLDITALIC"));
        System.out.println(Character.UnicodeBlock.forName("NUMBERFORMS"));
        System.out.println(Character.UnicodeBlock.forName("MALAYALAM") + "\n");

        // Use of(char ch) :
        System.out.println("Using UnicodeBlock.of(char ch) : ");
        System.out.println(Character.UnicodeBlock.of(' '));
        System.out.println(Character.UnicodeBlock.of('\u21ac') + "\n");

        // Use of(int UCPoint) :
        System.out.println("Using UnicodeBlock.of(int UCPoint) : ");
        System.out.println(Character.UnicodeBlock.of(1609));
        System.out.println(Character.UnicodeBlock.of(1565));
    }
}
```

## 输出

```java
Using UnicodeBlock.forName() :
OLD_ITALIC
NUMBER_FORMS
MALAYALAM

Using UnicodeBlock.of(char ch) :
BASIC_LATIN
ARROWS

Using UnicodeBlock.of(int UCPoint) :
ARABIC
ARABIC
```

## 注

`Character.UnicodeBlock` 类从 `Character.Subset` 类继承了其他方法，而 `Character.Subset` 类又继承了 `java.lang.Object` 类的方法。

有关 `java.lang.Object` 的更多详细信息，请参考：
- [Java 中的 Character.Subset 类](https://www.geeksforgeeks.org/java-lang-character-subset-class-java/)
- [Java 中的 Object 类](https://www.geeksforgeeks.org/object-class-in-java/)

本文由 **莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。