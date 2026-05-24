# Scala Char +(x: Byte)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-byte-method-with-example-4/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-4/)

利用 **+(x: Byte)** 方法求所述字符值与 Int 类型的‘x’之和。

> **方法定义:** def +(x: Byte): Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of +(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Byte) method 
        val result = 'D'.+(126)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
194

```

**例:2#**

```scala
// Scala program of +(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Byte) method
        val result = 'D'.+(-125)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-57

```