# 斯卡拉龙！=(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-long-x-byte-method-with-example/](https://www.geeksforgeeks.org/scala-long-x-byte-method-with-example/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。**！=(x: Byte)** 方法用于检查给定的 Long 和 Byte 值是否相等。

> **方法定义–**def！=(x:字节):布尔值
> 
> **返回–**如果该值不等于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program to explain working 
// of Long !=(x: Byte) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Byte) function
        val result = (-128).toLong.!= (-2^7:Byte)

        // Displays output
        println(result)

    }
} 

```

**输出:**

```scala
true
```

**例 2:**

```scala
// Scala program to explain working
// of Long !=(x: Byte) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Byte) function
        val result = 16.toLong.!= (2^4:Byte)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
true
```