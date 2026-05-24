# Scala Byte/(x:Double):Double

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-double-double-4/](https://www.geeksforgeeks.org/scala-byte-x-double-double-4/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法/(x:Double)方法用于返回该值与 x 的商。

> **方法定义:**字节/(x: Double): Double
> **返回类型:**返回该值与 x 的商。

示例#1:

```scala
// Scala program of Byte /(x: Double)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte /(x: Double) function 
        val result = (64.toByte)./(12:Double) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
5.33333333
```

示例 2:

```scala
// Scala program of Byte /(x: Double)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte /(x: Double) function 
        val result = (125.toByte)./(11:Double) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
11.363636363636363
```