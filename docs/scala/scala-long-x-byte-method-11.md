# Scala Long %(x: Byte)方法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-byte-method-11/](https://www.geeksforgeeks.org/scala-long-x-byte-method-11/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。当给定的长值除以字节值时，使用 **%(x: Byte)** 方法返回余数。

> **方法定义–**定义百分比(x:字节)
> 
> **返回–**返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Long %(x: Byte) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Byte) function
        val result = (165.toLong).%(2^4:Byte)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
3
```

**例 2:**

```scala
// Scala program to explain the working 
// of Long %(x: Byte) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Byte) function
        val result = (65.toLong).%(2^5:Byte)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
2
```