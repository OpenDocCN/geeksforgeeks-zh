# Scala Long -(x: Char)方法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-char-method-7/](https://www.geeksforgeeks.org/scala-long-x-char-method-7/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。 **-(x: Char)** 方法用于返回该值与给定值 x 之差。

> **方法定义–**def-(x:Char):Long
> 
> 返回–返回该值与 x 之差。

**示例#1:**

```scala
// Scala program to explain the working 
// of Long -(x: Char) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Int) function
        val result = (72.0021.toLong).-('A':Char)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
7

```