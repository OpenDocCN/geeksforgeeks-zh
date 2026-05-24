# Java中的`Character.valueOf()`示例

> 原文：[https://www.geeksforgeeks.org/character-valueof-in-java-with-examples/](https://www.geeksforgeeks.org/character-valueof-in-java-with-examples/)

`java.lang.Character.valueOf()`是Java中的一个内置方法，它返回一个表示指定字符值的`Character`实例。如果不需要新的`Character`实例，通常会优先使用该方法而不是构造函数`Character(char)`，因为该方法通过缓存频繁请求的值可能会产生显著更好的空间和时间性能。此方法将始终缓存范围`'\u0000'`到`'\u007F'`的值，并可能缓存此范围之外的其他值。

## 语法

```java
public static Character valueOf(char ch)
```

参数：
`ch` - 此参数指定字符。

## 返回值

这个方法返回一个代表`ch`的`Character`实例。

下面的程序演示了`java.lang.Character.valueOf()`函数：

## 程序1

```java
// Java program to demonstrate the
// Java.lang.Character.valueOf() method
// when the assigned char is a character

import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {
        // Create a character object
        Character c = new Character('z');

        // assign the primitive value to a character
        char ch = c.charValue();

        System.out.println("Character value of " + ch + " is " + c);
    }
}
```

**输出：**

```java
Character value of z is z
```

## 程序2

```java
// Java program to demonstrate the
// Java.lang.Character.valueOf() method
// when the assigned char is a number

import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {
        // Create a character object
        Character c = new Character('5');

        // assign the primitive value to a character
        char ch = c.charValue();

        System.out.println("Character value of " + ch + " is " + c);
    }
}
```

**输出：**

```java
Character value of 5 is 5
```