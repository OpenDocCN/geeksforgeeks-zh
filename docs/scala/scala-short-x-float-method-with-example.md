# Scala Short +(x: Float)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-short-x-float-method-with-example/](https://www.geeksforgeeks.org/scala-short-x-float-method-with-example/)

利用 **+(x: Float)** 方法求所述短值与 Float 类型的‘x’之和。

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
        val result = (999).+(10.4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1009.4

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
        val result = (-996).+(54.1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-941.9

```