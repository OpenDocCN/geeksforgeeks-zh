# Scala Double /(x: Short)法

> 原文:[https://www . geesforgeks . org/Scala-double-x-short-method-8/](https://www.geeksforgeeks.org/scala-double-x-short-method-8/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。 **/(x:短)**方法用于返回该值与给定值 x 的商。

> **方法定义–**def/(x:短):Double
> 
> **返回–**返回该值与 x 的商。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double /(x: Short) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Short) function
        val result = (321.0021.toDouble)./(13:Short)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
24.69246923076923

```