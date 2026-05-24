# Scala Char |(x: Int)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-int-method-with-example/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example/)

**|(x: Int)** 方法用于在参数列表中查找所述字符值和给定“x”的逐位“或”，该值必须为整数。

> **方法定义:** def|(x: Int): Int
> 
> **返回类型:**返回指定字符值和给定整数“x”的逐位或。

**例:1#**

```scala
// Scala program of |(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Int) method 
        val result = 'A'.|(5)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
69

```

**例:2#**

```scala
// Scala program of |(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Int) method
        val result = 'A'.|(9)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
73

```