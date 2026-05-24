# Scala Byte toByte()方法

> 原文:[https://www.geeksforgeeks.org/scala-byte-tobyte-method/](https://www.geeksforgeeks.org/scala-byte-tobyte-method/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。toByte()方法用于将指定的数字转换为 Byte 数据类型值。

> **方法定义:**(数字)。toByte
> 
> **返回类型:**返回转换后的字节值。

**示例#1:**

```scala
// Scala program of Byte toByte() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toByte method 
        val result = (13).toByte 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
13

```

**例 2:**

```scala
// Scala program of Byte toByte() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toByte method 
        val result = (123).toByte

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
123

```