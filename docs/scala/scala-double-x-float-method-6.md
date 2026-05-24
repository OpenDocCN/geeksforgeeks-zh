# Scala Double %(x: Float)法

> 原文:[https://www . geesforgeks . org/Scala-double-x-float-method-6/](https://www.geeksforgeeks.org/scala-double-x-float-method-6/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。当给定的 Double 值除以 Float 值时，使用 **%(x: Float)** 方法返回余数。

> **方法定义–**def %(x:Float)
> 
> 返回–返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double %(x: Float) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Float) function
        val result = (12.500001.toDouble).%(8:Float)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
4.500000999999999

```