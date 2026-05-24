# Scala Short +(x: Double)方法示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-double-method-with-example/](https://www.geeksforgeeks.org/scala-short-x-double-method-with-example/)

利用 **+(x: Double)** 方法求所述短值与 Double 类型的‘x’之和。

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
        val result = (1000).+(10.4311)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1010.4311

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
        val result = (-1000).+(54.1233)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-945.8767

```