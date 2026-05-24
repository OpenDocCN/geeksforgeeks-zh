# Scala Char +(x: Double)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-double-method-with-example/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example/)

利用 **+(x: Double)** 方法求所述字符值与 Double 类型的‘x’之和。

> **方法定义:** def +(x: Double): Double
> 
> **返回类型:**返回 Double。

**例:1#**

```scala
// Scala program of +(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Double) method 
        val result = 'E'.+(10.4311)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
79.4311

```

**例:2#**

```scala
// Scala program of +(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Double) method
        val result = 'E'.+(54.1233)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
123.1233

```