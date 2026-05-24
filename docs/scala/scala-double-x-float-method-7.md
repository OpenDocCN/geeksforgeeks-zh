# Scala Double *(x: Float)方法

> 原文:[https://www . geesforgeks . org/Scala-double-x-float-method-7/](https://www.geeksforgeeks.org/scala-double-x-float-method-7/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。使用 ***(x: Double)** 方法返回指定的 Double 值和 Float 值的乘积。

> **方法定义–**def *(x:Float)
> 
> 返回–返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Double *(x: Float) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Float) function
        val result = (13.002125.toDouble).*(5:Float)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
65.010625

```