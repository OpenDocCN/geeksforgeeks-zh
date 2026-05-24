# 斯卡拉浮动

T2】原文:[https://www . geeksforgeeks . org/Scala-float-x-int-method-with-example-3/](https://www.geeksforgeeks.org/scala-float-x-int-method-with-example-3/)

如果浮点值小于 Int 值，则使用 **< (x: Int)** 方法返回 true，否则返回 false。

> **方法定义:** (Float_Value)。< (Int_Value)
> 
> **返回类型:**如果浮点值小于 int 值则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Float <(x: int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: int) function
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
// Scala program of Float <(x: int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: int) function
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