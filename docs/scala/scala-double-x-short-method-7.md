# Scala Double *(x: Short)法

> 原文:[https://www . geesforgeks . org/Scala-double-x-short-method-7/](https://www.geeksforgeeks.org/scala-double-x-short-method-7/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。使用 ***(x: Short)** 方法返回指定的 Double 值和 Short 值的乘积。

> **方法定义–**def *(x:Short)
> 
> 返回–返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Double *(x: Short) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Short) function
        val result = (10.002200.toDouble).*(4:Short)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
40.0088

```