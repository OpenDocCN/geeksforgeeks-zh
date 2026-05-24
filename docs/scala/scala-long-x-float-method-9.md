# Scala Long *(x: Float)方法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-float-method-9/](https://www.geeksforgeeks.org/scala-long-x-float-method-9/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。使用 ***(x: Double)** 方法返回指定的 Long 值和 Float 值的乘积。

> **方法定义–**定义*(x:浮点)
> 
> **返回–**返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Long *(x: Float) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Float) function
        val result = (13.toLong).*(5:Float)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
65.0
```

**例 2:**

```scala
// Scala program to explain working of
// Long *(x: Float) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Float) function
        val result = (150.toLong).*(5:Float)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
750.0
```