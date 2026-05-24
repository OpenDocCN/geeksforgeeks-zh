# Scala 字节-(x: Double): Double

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-double-double-3/](https://www.geeksforgeeks.org/scala-byte-x-double-double-3/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法-(x:Double)方法用于返回该值与 x 的差值

> **方法定义:**字节-(x: Double): Double
> **返回类型:**返回该值的差 x。

示例#1:

```scala
// Scala program of Byte -(x: Double)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte -(x: Double) function 
        val result = (167.toByte).-(125:Double) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-213.0
```

示例 2:

```scala
// Scala program of Byte -(x: Double)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte -(x: Double) function 
        val result = (128.toByte).-(2:Double) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-130.0
```