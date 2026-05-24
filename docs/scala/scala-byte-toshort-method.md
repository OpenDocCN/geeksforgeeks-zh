# Scala Byte toShort()方法

> 原文:[https://www.geeksforgeeks.org/scala-byte-toshort-method/](https://www.geeksforgeeks.org/scala-byte-toshort-method/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。toShort()方法用于将指定的数字转换为短数据类型值。

> **方法定义:**(数字)。toShort
> 
> **返回类型:**返回转换后的短值。

**示例#1:**

```scala
// Scala program of Byte toShort() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toShort method 
        val result = (13).toShort

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
// Scala program of Byte toShort() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toShort method 
        val result = (123.4).toShort

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
123

```