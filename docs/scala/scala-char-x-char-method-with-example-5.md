# Scala Char /(x: Char)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-char-method-with-example-5/](https://www.geeksforgeeks.org/scala-char-x-char-method-with-example-5/)

利用 **/(x: Char)** 方法求出所述字符值与 Char 类型的‘x’的商。

> **方法定义:** def /(x: Char): Int
> 
> **返回类型:**返回整数。

**例:1#**

```scala
// Scala program of /(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Char) method 
        val result = 'D'./('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```

**例:2#**

```scala
// Scala program of /(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying /(x: Char) method
        val result = 'D'./('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```