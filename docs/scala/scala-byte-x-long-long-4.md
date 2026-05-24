# Scala 字节*(x:长):长

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-long-long-4/](https://www.geeksforgeeks.org/scala-byte-x-long-long-4/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法*(x:Long)方法用于返回该值与 x 的乘积。

> **方法定义:**字节*(x: Long): Long
> **返回类型:**返回该值与 x 的乘积。

示例#1:

```scala
// Scala program of Byte *(x: Long)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte *(x: Long) function 
        val result = (64.toByte).*(12:Long) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
768
```

示例 2:

```scala
// Scala program of Byte *(x: Long)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte *(x: Long) function 
        val result = (17.toByte).*(128:Long) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
2176
```