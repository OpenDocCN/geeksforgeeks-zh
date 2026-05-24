# Scala Float round()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-round-method-with-example/](https://www.geeksforgeeks.org/scala-float-round-method-with-example/)

**round()** 方法用于返回指定浮点值的舍入值。如果浮点值为 5.5 或大于 5.5 直到 5.9，则它将返回 6，否则如果浮点值为 5.0 或直到 5.4，则返回 5

> **方法定义:** (Float_Value)。轮次
> 
> **返回类型:**返回指定浮点值的舍入值。

**示例#1:**

```scala
// Scala program of Float round()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying round method
        val result = (5.4).round

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
5

```

**例 2:**

```scala
// Scala program of Float round()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying round method
        val result = (5.9).round

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
6

```