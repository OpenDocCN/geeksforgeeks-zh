# Scala Char +(x: Float)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-float-method-with-example/](https://www.geeksforgeeks.org/scala-char-x-float-method-with-example/)

利用 **+(x: Float)** 方法求所述字符值与 Float 类型的‘x’之和。

> **方法定义:** def +(x: Float): Float
> 
> **返回类型:**返回 Float。

**例:1#**

```scala
// Scala program of +(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Float) method 
        val result = 'E'.+(10.4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
79.4

```

**例:2#**

```scala
// Scala program of +(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Float) method
        val result = 'G'.+(54.1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
125.1

```