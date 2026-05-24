# Scala Char /(x: Long)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-long-method-with-example-8/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-8/)

利用 **/(x: Long)** 方法求所述字符值与 Long 类型的‘x’的商。

> **方法定义:** def /(x: Long): Long
> 
> **返回类型:**返回 Long。

**例:1#**

```scala
// Scala program of /(x: Long)
// method

// Creating object
object GfG 
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Long) method 
        val result = 'D'./(100000L)

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
// Scala program of /(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Long) method
        val result = 'D'./(-100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```