# Scala Float ceil()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-ceil-method-with-example/](https://www.geeksforgeeks.org/scala-float-ceil-method-with-example/)

使用 **ceil()** 方法返回大于或等于给定数值的数值。

> **方法定义:**定义上限:浮动
> 
> **返回类型:**返回一个大于等于给定数的数。

**示例#1:**

```scala
// Scala program of Float ceil()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ceil method
        val result = (5.4).ceil

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
6.0

```

**例 2:**

```scala
// Scala program of Float ceil()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ceil method
        val result = (-3.8).ceil

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-3.0

```