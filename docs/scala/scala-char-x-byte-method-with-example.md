# Scala Char |(x: Byte)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-byte-method-with-example/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example/)

**|(x: Byte)** 方法用于在必须是 Byte 类型的参数列表中找到所述字符值和给定“x”的逐位或。

> **方法定义:** def|(x: Byte): Byte
> 
> **返回类型:**返回指定字符值和给定字节类型“x”的逐位或。

**例:1#**

```scala
// Scala program of |(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Byte) method 
        val result = 'B'.|(121)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
123

```

**例:2#**

```scala
// Scala program of |(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Byte) method
        val result = 'B'.|(-128)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-62

```