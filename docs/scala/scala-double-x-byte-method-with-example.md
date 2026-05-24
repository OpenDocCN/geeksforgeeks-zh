# Scala Double -(x: Byte)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-double-x-byte-method-with-example/](https://www.geeksforgeeks.org/scala-double-x-byte-method-with-example/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。利用 **-(x: Byte)** 方法得到给定 Double 和 Byte 值的差值。

> **方法定义–**def-(x:字节):Double
> 
> **返回–**返回该值与 x 的差值。

**示例#1:**

```scala
// Scala program to explain working 
// of Double -(x: Byte) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Byte) function
        val result = (66.00123).toDouble.- (50:Byte)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
16.001230000000007

```