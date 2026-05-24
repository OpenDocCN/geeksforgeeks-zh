# Scala Char +(x: Short)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-short-method-with-example-4/](https://www.geeksforgeeks.org/scala-char-x-short-method-with-example-4/)

利用 **+(x: Short)** 方法求所述字符值与 Short 类型的‘x’之和。

> **方法定义:** def +(x: Short): Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of +(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Short) method 
        val result = 'D'.+(1000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1068

```

**例:2#**

```scala
// Scala program of +(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Short) method
        val result = 'D'.+(-1000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-932

```