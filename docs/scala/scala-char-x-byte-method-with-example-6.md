# Scala Char /(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-byte-method-with-example-6/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-6/)

利用 **/(x: Byte)** 方法求出所述字符值与 Byte 类型的‘x’的商。

> **方法定义:** def /(x: Byte): Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of /(x: Byte)
// method

// Creating object
object GfG 
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Byte) method 
        val result = 'D'./(126)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```

**例:2#**

```scala
// Scala program of /(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Byte) method
        val result = 'D'./(-11)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-6

```