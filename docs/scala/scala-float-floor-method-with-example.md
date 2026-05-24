# Scala Float floor()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-floor-method-with-example/](https://www.geeksforgeeks.org/scala-float-floor-method-with-example/)

**floor()** 方法用于返回小于或等于给定浮点数的浮点数。

> **方法定义:** (Float_Number)。地面
> 
> **返回类型:**返回小于等于给定浮点数的浮点数。

**示例#1:**

```scala
// Scala program of Float floor()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying floor method
        val result = (5.4).floor

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
5.0

```

**例 2:**

```scala
// Scala program of Float floor()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying floor method
        val result = (-3.8).floor

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-4.0

```