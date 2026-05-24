# Scala Int isWhole()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-isw hole-method-with-example/](https://www.geeksforgeeks.org/scala-int-iswhole-method-with-example/)

如果指定的整数没有小数部分，则使用 **isWhole()** 方法返回真，否则返回假。

> **方法定义:** (Int_Number)。isWhole
> 
> **返回类型:**如果指定的整数没有小数部分，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Int isWhole()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isWhole method
        val result = (5).isWhole

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
// Scala program of Int isWhole()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isWhole method
        val result = (5.0).isWhole

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```