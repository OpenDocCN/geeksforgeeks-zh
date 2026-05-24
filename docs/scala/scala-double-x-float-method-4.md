# Scala 双> (x: Float)法

> 原文:[https://www . geesforgeks . org/Scala-double-x-float-method-4/](https://www.geeksforgeeks.org/scala-double-x-float-method-4/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。如果该值大于 x，则使用 **> (x: Float)** 方法返回真，否则返回假。

> **方法定义–**def>(x:Float):布尔值
> 
> **返回–**如果该值大于 x，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double >(x: Float) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: Float) function
        val result = (12.00123.toDouble).>(8:Float)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
true

```