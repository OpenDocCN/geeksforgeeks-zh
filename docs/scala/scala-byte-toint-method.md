# Scala Byte toInt()方法

> 原文:[https://www.geeksforgeeks.org/scala-byte-toint-method/](https://www.geeksforgeeks.org/scala-byte-toint-method/)

在 Scala 中，Byte 是一个 8 位有符号整数(相当于 Java 的字节基元类型)。toInt()方法用于将指定的数字转换为 Int 数据类型值。

> **方法定义:**(数字)。toInt
> 
> **返回类型:**返回转换后的整数值。

**示例#1:**

```scala
// Scala program of Byte toInt() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toInt method 
        val result = (13).toInt

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
// Scala program of Byte toInt() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toInt method 
        val result = (123.4).toInt

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
123

```