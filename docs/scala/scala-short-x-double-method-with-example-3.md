# Scala Short %(x: Double)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-double-method-with-example-3/](https://www.geeksforgeeks.org/scala-short-x-double-method-with-example-3/)

利用 **%(x: Double)** 方法求所述短值除以 Double 类型的“x”的余数。

> **方法定义:** def %(x: Double): Double
> 
> **返回类型:**返回 Double。

**例:1#**

```scala
// Scala program of %(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Double) method 
        val result = (1000).%(10.45)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
7.2500000000000675

```

**例:2#**

```scala
// Scala program of %(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Double) method
        val result = (994).%(15.76)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1.1200000000000134

```