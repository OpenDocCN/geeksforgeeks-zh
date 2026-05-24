# Scala Char -(x: Double)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-double-method-with-example-2/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-2/)

利用 **-(x: Double)** 方法找出所述字符值与 Double 类型的‘x’之间的差异。

> **方法定义:** def -(x: Double): Double
> 
> **返回类型:**返回 Double。

**例:1#**

```scala
// Scala program of -(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Double) method 
        val result = 'A'.-(11.6574)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
53.3426

```

**例:2#**

```scala
// Scala program of -(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying -(x: Double) method
        val result = 'D'.-(19.6578)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
48.3422

```