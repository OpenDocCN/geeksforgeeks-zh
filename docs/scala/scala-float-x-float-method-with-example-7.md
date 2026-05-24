# Scala Float %(x: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-float-method-with-example-7/](https://www.geeksforgeeks.org/scala-float-x-float-method-with-example-7/)

当第一个浮点值除以第二个浮点值时，使用 **%(x: Float)** 方法返回余数。

> **方法定义:** (First_Float_Value)。%(秒 _ 浮点 _ 值)
> 
> **返回类型:**当第一个浮点值除以第二个浮点值时，返回余数。

**示例#1:**

```scala
// Scala program of Float %(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Float) function
        val result = (65.0).%(65.0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0.0

```

**例 2:**

```scala
// Scala program of Float %(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Float) function
        val result = (100.0).%(65.0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
35.0

```