# 斯卡拉浮动

T2】原文:[https://www . geeksforgeeks . org/Scala-float-x-double-method-with-example-3/](https://www.geeksforgeeks.org/scala-float-x-double-method-with-example-3/)

如果浮点值小于双精度值，则使用 **< (x: Double)** 方法返回真，否则返回假。

> **方法定义:** (Float_Value)。<(双值)
> 
> **返回类型:**如果浮点值小于双精度值，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float <(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Double) function
        val result = (100.0).<(50)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of Float <(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Double) function
        val result = (50.0).<(100)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```