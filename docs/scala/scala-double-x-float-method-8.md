# Scala Double /(x: Float)方法

> 原文:[https://www . geesforgeks . org/Scala-double-x-float-method-8/](https://www.geeksforgeeks.org/scala-double-x-float-method-8/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。 **/(x: Float)** 方法用于返回该值与给定值 x 的商。

> **方法定义–**def/(x:Float):Double
> 
> **返回–**返回该值与 x 的商。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double /(x: Float) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Float) function
        val result = (12.0021.toDouble)./(4:Float)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
3.000525

```