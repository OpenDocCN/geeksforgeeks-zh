# Scala Double /(x: Double)法

> 原文:[https://www . geesforgeks . org/Scala-double-x-double-method-8/](https://www.geeksforgeeks.org/scala-double-x-double-method-8/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。 **/(x: Double)** 方法用于返回该值与给定值 x 的商。

> **方法定义–**def/(x:Double):Double
> 
> **返回–**返回该值与 x 的商。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double /(x: Double) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Double) function
        val result = (12.251100.toDouble)./(3:Double)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
4.083699999999999

```