# Scala Int isValidLong()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-is validlong-method-with-example/](https://www.geeksforgeeks.org/scala-int-isvalidlong-method-with-example/)

如果指定的 int 数为零或在 scala.long MinValue 和 MaxValue 范围内，则使用 **isValidLong()** 方法返回 true 否则返回 false。

> **方法定义:** (Int_Number)。isValidLong
> 
> **返回类型:**如果指定的数字为零或在 scala.long MinValue 和 MaxValue 范围内，则返回 true 否则返回 false。

**示例#1:**

```scala
// Scala program of Int isValidLong()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidLong method
        val result = (0).isValidLong

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
// Scala program of Int isValidLong()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidLong method
        val result = (5).isValidLong

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```