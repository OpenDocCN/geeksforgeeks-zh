# Scala 字节%(x: Float): Float

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-float-float/](https://www.geeksforgeeks.org/scala-byte-x-float-float/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法% x:Float 方法用于返回该值除以 x 的余数

> **方法定义:**字节%(x: Float): Float
> **返回类型:**它返回这个值除以 x 的余数。

示例#1:

```scala
// Scala program of Byte %(x: Float)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte %(x: Float) function 
        val result = (100.toByte).%(3:Float) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
1.0
```

示例 2:

```scala
// Scala program of Byte %(x: Float)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte %(x: Float) function 
        val result = (167.toByte).%(3:Float) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-2.0
```