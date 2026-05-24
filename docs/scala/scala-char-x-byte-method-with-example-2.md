# Scala Char ^(x:字节)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-byte-method-with-example-2/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-2/)

**^(x:字节)**方法用于在自变量列表中找到所述字符和类型字节的给定“x”的逐位异或。

> **方法定义:** def ^(x:字节):Int
> 
> **返回类型:**返回指定字符和给定字节类型“x”的逐位异或。

**例:1#**

```scala
// Scala program of ^(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ^(x: Byte) method 
        val result = 'B'.^(127)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
61

```

**例:2#**

```scala
// Scala program of ^(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ^(x: Byte) method
        val result = 'B'.^(-128)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-62

```