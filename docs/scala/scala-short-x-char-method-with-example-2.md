# Scala Short *(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-char-method-with-example-2/](https://www.geeksforgeeks.org/scala-short-x-char-method-with-example-2/)

使用 ***(x: Char)** 方法来寻找所述短值与 Char 类型的‘x’的乘积。

> **方法定义:** def *(x: Char): Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of *(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Char) method 
        val result = (1000).*('e')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
101000

```

**例:2#**

```scala
// Scala program of *(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Char) method
        val result = (999).*('a')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
96903

```