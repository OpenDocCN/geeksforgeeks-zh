# Scala Double < =(x: Double)法

> 原文:[https://www . geesforgeks . org/Scala-double-x-double-method-2/](https://www.geeksforgeeks.org/scala-double-x-double-method-2/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。如果该值小于或等于 x，则使用 **< =(x: Double)** 方法返回真，否则返回假。

> **方法定义–**def<=(x:Double):布尔值
> 
> **返回–**如果该值小于或等于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double <=(x: Double) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <=(x: Double) function
        val result = (12.0021.toDouble).<=(8:Double)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```