# Scala Int isValidShort()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-is valid short-method-with-example/](https://www.geeksforgeeks.org/scala-int-isvalidshort-method-with-example/)

如果指定的 int 数为零或在 scala.short MinValue 和 MaxValue 的范围内，则使用 **isValidShort()** 方法返回 true 否则返回 false。

> **方法定义:** (Int_Number)。isValidShort
> 
> **返回类型:**如果指定的数字为零或在 scala.short MinValue 和 MaxValue 范围内，则返回 true 否则返回 false。

**示例#1:**

```scala
// Scala program of Int isValidShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidShort method
        val result = (0).isValidShort

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
// Scala program of Int isValidShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidShort method
        val result = (5).isValidShort

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```