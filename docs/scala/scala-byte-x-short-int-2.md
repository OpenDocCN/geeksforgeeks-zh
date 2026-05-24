# Scala Byte %(x: Short): Int

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-short-int-2/](https://www.geeksforgeeks.org/scala-byte-x-short-int-2/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法% x:Byte 方法用于返回该值除以 x 的余数

> **方法定义:** Byte %(x: Byte): Int
> **返回类型:**返回该值除以 x 的余数。

示例#1:

```scala
// Scala program of Byte %(x: Byte)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte %(x: Byte) function 
        val result = (100.toByte).%(3:Byte) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
1
```

示例 2:

```scala
// Scala program of Byte %(x: Byte)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte %(x: Byte) function 
        val result = (167.toByte).%(3:Byte) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-2
```