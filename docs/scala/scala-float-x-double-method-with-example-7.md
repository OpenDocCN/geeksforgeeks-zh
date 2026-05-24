# Scala Float %(x: Double)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-double-method-with-example-7/](https://www.geeksforgeeks.org/scala-float-x-double-method-with-example-7/)

当给定的浮点值除以双精度值时，使用 **%(x: Double)** 方法返回余数。

> **方法定义:** (Float_Value)。%(双精度值)
> 
> **返回类型:**当给定的浮点值除以双精度值时，返回余数。

**示例#1:**

```scala
// Scala program of Float %(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Double) function
        val result = (7.0).%(3)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1.0

```

**例 2:**

```scala
// Scala program of Float %(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Double) function
        val result = (65.0).%(65)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0.0

```