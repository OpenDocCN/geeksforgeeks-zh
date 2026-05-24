# Scala 双-(x: Short)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-double-x-short-method-with-example-2/](https://www.geeksforgeeks.org/scala-double-x-short-method-with-example-2/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。利用 **-(x: Short)** 方法得到给定的双短值之差。

> **方法定义–**def-(x:Short):Double
> 
> **返回–**返回该值与 x 的差值。

**示例#1:**

```scala
// Scala program to explain working 
// of Double -(x: Short) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Short) function
        val result = (66.00123).toDouble.- (50:Short)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
16.001230000000007

```