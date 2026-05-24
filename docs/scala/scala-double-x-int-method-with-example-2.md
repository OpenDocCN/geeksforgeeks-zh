# Scala Double -(x: Int)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-double-x-int-method-with-example-2/](https://www.geeksforgeeks.org/scala-double-x-int-method-with-example-2/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。利用 **-(x: Int)** 方法得到给定 Double 和 Int 值的差。

> **方法定义–**def-(x:Int):Double
> 
> **返回–**返回该值与 x 的差值。

**示例#1:**

```scala
// Scala program to explain working 
// of Double -(x: Int) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Int) function
        val result = (66.01230).toDouble.- (60:Int)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
6.012299999999996

```