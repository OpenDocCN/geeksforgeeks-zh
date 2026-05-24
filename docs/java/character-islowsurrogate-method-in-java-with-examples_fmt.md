# Java 中的 Character.isLowSurrogate() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/character-islowsurrogate-method-in-java-with-examples/](https://www.geeksforgeeks.org/character-islowsurrogate-method-in-java-with-examples/)

## 方法介绍

`java.lang.Character.isLowSurrogate(char ch)` 是 Java 中的一个内置方法，它确定给定的 `char` 值是否是 Unicode 低代理代码单元（也称为尾随代理代码单元）。这些值本身并不表示字符，而是用于表示 UTF-16 编码中的补充字符。

## 语法

```java
public static boolean isLowSurrogate(char ch)
```

## 参数

该功能接受一个强制参数 `ch`，指定要测试的字符。

## 返回值

函数返回一个布尔值。如果字符值介于 `MIN_LOW_SURROGATE` 和 `MAX_LOW_SURROGATE` 之间（含这两个值），则返回值为 `true`，否则返回值为 `false`。

## 示例程序

下面的程序说明了 `Character.isLowSurrogate()` 方法：

### 程序 1

```java
// Java program to illustrate the
// Character.isLowSurrogate() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2
        char c1 = '\udc25', c2 = 'h';

        // assign isLowSurrogate results of
        // c1, c2 to boolean primitives bool1, bool2
        boolean bool1 = Character.isLowSurrogate(c1);
        System.out.println("c1 is a Unicode low-surrogate ? " + bool1);

        boolean bool2 = Character.isLowSurrogate(c2);
        System.out.println(c2 + " is a Unicode low-surrogate ? " + bool2);
    }
}
```

### 输出

```java
c1 is a Unicode low-surrogate ? true
h is a Unicode low-surrogate ? false
```

### 程序 2

```java
// Java program to illustrate the
// Character.isLowSurrogate() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2
        char c1 = '\udc29', c2 = 'x';

        // assign isLowSurrogate results of
        // c1, c2 to boolean primitives bool1, bool2
        boolean bool1 = Character.isLowSurrogate(c1);
        System.out.println("c1 is a Unicode low-surrogate ? " + bool1);

        boolean bool2 = Character.isLowSurrogate(c2);
        System.out.println(c2 + " is a Unicode low-surrogate ? " + bool2);
    }
}
```

### 输出

```java
c1 is a Unicode low-surrogate ? true
x is a Unicode low-surrogate ? false
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isLowSurrogate(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isLowSurrogate(char))