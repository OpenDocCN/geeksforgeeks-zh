# Scala Long *(x: Byte)方法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-byte-method-10/](https://www.geeksforgeeks.org/scala-long-x-byte-method-10/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。使用 ***(x: Byte)** 方法返回指定的 Long 值和 Byte 值的乘积。

> **方法定义–**def *(x:字节)
> 
> **返回–**返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Long *(x: Byte) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Byte) function
        val result = (13.toLong).*(2^4:Byte)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
78
```

**例 2:**

```scala
// Scala program to explain working of
// Long *(x: Byte) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Byte) function
        val result = (150.toLong).*(2^5:Byte)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
1050
```