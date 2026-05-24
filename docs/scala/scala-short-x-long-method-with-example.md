# Scala Short +(x: Long)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-short-x-long-method-with-example/](https://www.geeksforgeeks.org/scala-short-x-long-method-with-example/)

利用 **+(x: Long)** 方法求所述短值与 Long 类型的‘x’之和。

> **方法定义:** def +(x: Long): Long
> 
> **返回类型:**返回 Long。

**例:1#**

```scala
// Scala program of +(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Long) method 
        val result = (998).+(100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
100998

```

**例:2#**

```scala
// Scala program of +(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Long) method
        val result = (111).+(-100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-99889

```