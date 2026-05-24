# Scala Double -(x: Double)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-double-x-double-method-with-example-2/](https://www.geeksforgeeks.org/scala-double-x-double-method-with-example-2/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。利用 **-(x: Double)** 方法得到给定 Double 和 Double 值的差。

> **方法定义–**def-(x:Char):Double
> 
> **返回–**返回该值与 x 的差值。

**示例#1:**

```scala
// Scala program to explain working 
// of Double -(x: Double) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Double) function
        val result = (66.01230).toDouble.- (65.00000:Double)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
1.0122999999999962

```