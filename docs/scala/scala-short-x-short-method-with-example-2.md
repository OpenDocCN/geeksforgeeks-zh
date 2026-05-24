# Scala Short +(x: Short)方法示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-short-method-with-example-2/](https://www.geeksforgeeks.org/scala-short-x-short-method-with-example-2/)

利用 **+(x: Short)** 方法求所述 Short 值与 Short 类型的‘x’之和。

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
        val result = (111).+(1000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1111

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
        val result = (999).+(-1000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-1

```