# Scala Long *(x: Double)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-double-method-9/](https://www.geeksforgeeks.org/scala-long-x-double-method-9/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。使用 ***(x: Double)** 方法返回指定的 Long 值和 Double 值的乘积。

> **方法定义–**def *(x:长)
> 
> **返回–**返回该值与 x 的按位“与”

**示例#1:**

```scala
// Scala program to explain working of
// Long *(x: Double) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Double) function
        val result = (13.toLong).*(5:Double)

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
// Long *(x: Double) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Double) function
        val result = (150.toLong).*(5:Double)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
750.0
```