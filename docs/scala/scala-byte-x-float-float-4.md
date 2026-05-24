# Scala 字节/(x: Float): Float

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-float-float-4/](https://www.geeksforgeeks.org/scala-byte-x-float-float-4/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法/(x:Float)方法用于返回该值与 x 的商。

> **方法定义:** Byte /(x: Float): Float
> **返回类型:**返回该值与 x 的商。

示例#1:

```scala
// Scala program of Byte /(x: Float)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte /(x: Float) function 
        val result = (64.toByte)./(12:Float) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
5.3333335
```

示例 2:

```scala
// Scala program of Byte /(x: Float)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte /(x: Float) function 
        val result = (125.toByte)./(11:Float) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
11.363636
```