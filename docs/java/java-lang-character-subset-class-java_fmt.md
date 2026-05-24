# Java中的`java.lang.Character.Subset`类

> 原文：[`https://www.geeksforgeeks.org/java-lang-character-subset-class-java/`](https://www.geeksforgeeks.org/java-lang-character-subset-class-java/)

`Character.Subset`类代表Unicode字符集（使用十六进制值表示字符的标准——16位）的特定子集。它在字符集内定义的子集是`UnicodeBlock`块。

## 声明

```java
public static class Character.Subset
   extends Object
```

## 构造方法

*   `protected Character.Subset(String name)`：构建新的子集实例。

## 方法

### `equals()`

`java.lang.Character.Subset.equals()`告诉两个`Subset`对象是否相等。

**语法：**

```java
public final boolean equals(Object o)
```

**参数：**
*   `o`：要比较的对象。

**返回值：**
*   `true`：如果`o`等于参数对象，否则为`false`。

### `hashCode()`

`java.lang.Character.Subset.hashCode()`返回子集的`hashCode`值。

**语法：**

```java
public final int hashCode()
```

**参数：**
*   无。

**返回值：**
*   参数对象的`hashCode`。

### `toString()`

`java.lang.Character.Subset.toString()`返回子集的名称。

**语法：**

```java
public final String toString()
```

**参数：**
*   无。

**返回值：**
*   参数对象的字符串表示。

## 示例代码

```java
// Java Program illustrating the use of Character.Subset class Methods.

import java.lang.*;

public class CharacterSubsetDemo extends Character.Subset {
   CharacterSubsetDemo(String s) {
      // Use of super keyword :
      // Invokes immediate parent class constructor.
      super(s);
   }

   public static void main(String[] args) {
      // Initializing two Subsets.
      CharacterSubsetDemo a = new CharacterSubsetDemo("geeks");
      CharacterSubsetDemo b = new CharacterSubsetDemo("for");

      // use of equals() :
      boolean check2 = a.equals(a);
      System.out.println("Is a equals a ? : " + check2);
      check2 = b.equals(a);
      System.out.println("Is b equals a ? : " + check2);
      System.out.println();

      // Use of hashCode() :
      int check1 = a.hashCode();
      System.out.println("hashCode " + a + " : " + check1);
      check1 = b.hashCode();
      System.out.println("hashCode " + b + " : " + check1);
      System.out.println();

      // Use of toString() :
      System.out.println("a : " + a.toString());
      System.out.println("b : " + b.toString());
   }
}
```

## 输出

```
Is a equals a ? : true
Is b equals a ? : false

hashCode geeks : 366712642
hashCode for : 1829164700

a : geeks
b : for
```

## 注

`java.lang.Character.Subset`类从`java.lang.Object`类继承其他方法。有关`java.lang.Object`的详细信息，请参考：[Java中的Object类](https://www.geeksforgeeks.org/object-class-in-java/)。

本文由 **莫希特·古普塔 _OMG 供稿😀**。如果你喜欢GeeksforGeeks并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。