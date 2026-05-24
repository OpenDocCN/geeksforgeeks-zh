# Scala Char |(x: Long)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-long-method-with-example/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example/)

**|(x: Long)** 方法用于在参数列表中查找所述字符值和给定“x”的逐位“或”，参数列表必须是 Long 类型。

> **方法定义:** def |(x: Long): Long
> 
> **返回类型:**返回指定字符值的位或，给定长类型“x”。

**例:1#**

```scala
// Scala program of |(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Long) method 
        val result = 'A'.|(100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
100065

```

**例:2#**

```scala
// Scala program of |(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Long) method
        val result = 'A'.|(-100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-99999

```