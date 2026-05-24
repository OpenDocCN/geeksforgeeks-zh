# Scala Double *(x: Double)方法

> 原文:[https://www . geesforgeks . org/Scala-double-x-double-method-7/](https://www.geeksforgeeks.org/scala-double-x-double-method-7/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。使用 ***(x: Double)** 方法返回指定的 Double 值和 Double 值的乘积。

> **方法定义–**def *(x:Long)
> 
> 返回–返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Double *(x: Double) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Double) function
        val result = (13.00215.toDouble).*(5:Double)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
65.01075

```