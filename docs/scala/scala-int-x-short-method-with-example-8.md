# 斯卡拉国际

T2】原文:[https://www . geeksforgeeks . org/Scala-int-x-short-method-with-example-8/](https://www.geeksforgeeks.org/scala-int-x-short-method-with-example-8/)

如果指定的 int 值小于 Short 值，则使用 **< (x: Short)** 方法返回 true，否则返回 false。

> **方法定义:** (Int_Value)。<(短值)
> 
> **返回类型:**如果指定的 int 值小于短值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int <(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <(x: Short) function
        val result = (100).<(110)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of Int <(x: short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <(x: short) function
        val result = (50).<(10)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```