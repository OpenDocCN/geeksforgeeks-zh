# Scala Float is finity()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-is infinity-method-with-example/](https://www.geeksforgeeks.org/scala-float-isinfinity-method-with-example/)

如果指定的浮点值为无穷大，则使用 **isInfinity()** 方法返回真，否则返回假。

> **方法定义:**(数字)。
> 返回类型:如果指定的浮点值为无穷大，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float isInfinity()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isInfinity method
        val result = (5.4).isInfinity

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
// Scala program of Float isInfinity()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isInfinity method
        val result = (7/3).isInfinity

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```