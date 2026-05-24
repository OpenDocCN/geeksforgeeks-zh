# Scala Double %(x: Byte)方法

> 原文:[https://www.geeksforgeeks.org/scala-double-x-byte-method-6/](https://www.geeksforgeeks.org/scala-double-x-byte-method-6/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。当给定的 Double 值除以 Byte 值时，使用 **%(x: Byte)** 方法返回余数。

> **方法定义–**def %(x:Byte)
> 
> 返回–返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double %(x: Byte) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Byte) function
        val result = (16.01255.toDouble ).%(2^4:Byte)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
4.012550000000001

```