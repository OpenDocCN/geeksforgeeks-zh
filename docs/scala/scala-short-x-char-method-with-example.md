# Scala Short +(x: Char)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-short-x-char-method-with-example/](https://www.geeksforgeeks.org/scala-short-x-char-method-with-example/)

利用 **+(x: Char)** 方法，求出所述短值与 Char 类型的‘x’之和。

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
        val result = (1000).+('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1065

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
        val result = (-1000).+('F')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-930

```