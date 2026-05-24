# Scala 短-(x: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-float-method-with-example-4/](https://www.geeksforgeeks.org/scala-short-x-float-method-with-example-4/)

利用 **-(x: Float)** 方法找出所述短值与 Float 类型的‘x’之间的差异。

> **方法定义:** def -(x: Float): Float
> 
> **返回类型:**返回 Float。

**例:1#**

```scala
// Scala program of -(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Float) method 
        val result = (1000).-(13.7)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
986.3

```

**例:2#**

```scala
// Scala program of -(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Float) method
        val result = (-1000).-(17.9)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-1017.9

```