# Scala Char +(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-char-method-with-example-3/](https://www.geeksforgeeks.org/scala-char-x-char-method-with-example-3/)

利用 **+(x: Char)** 方法求所述字符值与 Char 类型的‘x’之和。

> **方法定义:** def +(x: Char): Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of +(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Char) method 
        val result = 'E'.+('A')

        // Displays output
        println(result)

    }
} 

```

**Output:**

```scala
134

```

**例:2#**

```scala
// Scala program of +(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Char) method
        val result = 'D'.+('F')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
138

```