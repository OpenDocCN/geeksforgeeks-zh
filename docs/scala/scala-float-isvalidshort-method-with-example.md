# Scala Float isValidShort()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-is valid short-method-with-example/](https://www.geeksforgeeks.org/scala-float-isvalidshort-method-with-example/)

如果指定的数字为零或在标量范围内，则使用 **isValidShort()** 方法返回真。短的 MinValue 和 MaxValue 否则返回 false。

> **方法定义:** (Float_Number)。isValidShort
> 
> **返回类型:**如果指定的数字为零或在标量范围内，则返回真。短的 MinValue 和 MaxValue 否则返回 false。

**示例#1:**

```scala
// Scala program of Float isValidShort()
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
// Scala program of Float isValidShort()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidShort method
        val result = (5.9).isValidShort

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```