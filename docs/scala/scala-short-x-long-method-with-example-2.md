# Scala 短*(x:长)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-long-method-with-example-2/](https://www.geeksforgeeks.org/scala-short-x-long-method-with-example-2/)

利用 ***(x: Long)** 方法求所述短值与 Long 类型的‘x’的乘积。

> **方法定义:** def *(x: Long): Long
> 
> **返回类型:**返回 Long。

**例:1#**

```scala
// Scala program of *(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Long) method 
        val result = (674).*(100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
67400000

```

**例:2#**

```scala
// Scala program of *(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Long) method
        val result = (-1000).*(-100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
100000000

```