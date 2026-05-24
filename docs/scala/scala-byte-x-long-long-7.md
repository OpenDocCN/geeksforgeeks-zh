# Scala Byte +(x: Long): Long

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-long-long-7/](https://www.geeksforgeeks.org/scala-byte-x-long-long-7/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法+(x:Long)方法用于返回该值与 x 的和

> **方法定义:** Byte +(x: Long): Long
> **返回类型:**返回这个值的和乘以 x。

示例#1:

```scala
// Scala program of Byte +(x: Long)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte +(x: Long) function 
        val result = (167.toByte).+(125:Long) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
36
```

示例 2:

```scala
// Scala program of Byte +(x: Long)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte +(x: Long) function 
        val result = (167.toByte).+(2:Long) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-87
```