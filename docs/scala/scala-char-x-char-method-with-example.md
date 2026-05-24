# Scala Char |(x: Char)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-char-method-with-example/](https://www.geeksforgeeks.org/scala-char-x-char-method-with-example/)

**|(x: Char)** 方法用于在参数列表中找到所述字符值和给定的“x”的逐位或。

> **方法定义:** def|(x: Char): Int
> 
> **返回类型:**返回指定字符值和给定“x”的逐位或。

**例:1#**

```scala
// Scala program of |(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Char) method 
        val result = 'A'.|('1')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
113

```

**例:2#**

```scala
// Scala program of |(x: Char)
// method

// Creating object
object GfG
{ 

    `// Main method
    def main(args:Array[String])
    {

        // Applying |(x: Char) method
        val result = 'A'.|('A')

        // Displays output
        println(result)

    }`
} 
```

**Output:**

```scala
65

```