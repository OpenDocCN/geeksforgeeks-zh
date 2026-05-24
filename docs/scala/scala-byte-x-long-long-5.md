# 标量字节^(x:长):长

> 原文:[https://www.geeksforgeeks.org/scala-byte-x-long-long-5/](https://www.geeksforgeeks.org/scala-byte-x-long-long-5/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。方法^(x:Long)方法用于返回该值和 x 的按位异或

> **方法定义:**字节^(x:长):长
> **返回类型:**它返回这个值和 x 的按位异或。

示例#1:

```scala
// Scala program of Byte ^(x: Long)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte ^(x: Long) function 
        val result = (110.toByte).^(2:Long) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
108
```

示例 2:

```scala
// Scala program of Byte ^(x: Long)
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Byte ^(x: Long) function 
        val result = (128.toByte).^(11:Long) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-117
```