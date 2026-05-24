# Scala Byte < =（x： Byte）： 布尔值

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-byte-boolean-3/](https://www.geeksforgeeks.org/scala-byte-x-byte-boolean-3/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。如果该值小于或等于 x，则使用方法< =(x:Byte)方法返回 true，否则返回 false。

> **方法定义:**字节< =(x:字节):布尔值
> **返回类型:**如果该值小于或等于 x，则返回真，否则返回假。

示例#1:

```scala
// Scala program of Byte <=(x: Byte)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte <=(x: Byte) function 
        val result = (64.toByte).<=(12:Byte) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false
```

示例 2:

```scala
// Scala program of Byte <=(x: Byte)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte <=(x: Byte) function 
        val result = (25.toByte).<=(111:Byte) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true
```