# Scala Byte ==(x: Long):布尔值

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-long-boolean-4/](https://www.geeksforgeeks.org/scala-byte-x-long-boolean-4/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。如果该值等于 x，则使用方法==(x:Long)方法返回 true，否则返回 false。

> **方法定义:**Byte = =(x:Long):Boolean
> **返回类型:**如果该值等于 x 则返回 true，否则返回 false。

示例#1:

```scala
// Scala program of Byte ==(x: Long)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte ==(x: Long) function 
        val result = (64.toByte).==(64:Long) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true
```

示例 2:

```scala
// Scala program of Byte ==(x: Long)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte ==(x: Long) function 
        val result = (25.toByte).==(111:Long) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false
```