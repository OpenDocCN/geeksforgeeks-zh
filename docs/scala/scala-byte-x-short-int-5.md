# Scala 字节*(x:短):Int

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-short-int-5/](https://www.geeksforgeeks.org/scala-byte-x-short-int-5/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法*(x:Short)用于返回该值与 x 的乘积

> **方法定义:** Byte *(x: Short): Int
> **返回类型:**它返回这个值和 x 的乘积。

示例#1:

```scala
// Scala program of Byte *(x: Short)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte *(x: Short) function 
        val result = (64.toByte).*(12:Short) 

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
// Scala program of Byte *(x: Short)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte *(x: Short) function 
        val result = (17.toByte).*(128:Short) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
2176
```