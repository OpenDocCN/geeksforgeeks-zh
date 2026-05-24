# Scala Map toString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-tostring-method-with-example/](https://www.geeksforgeeks.org/scala-map-tostring-method-with-example/)

**toString()** 方法用于显示 Scala 映射中的字符串。

> **方法定义:** def toString(): String
> 
> **返回类型:**从指定的映射中返回一个字符串。

**示例#1:**

```scala
// Scala program of toString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying toString method
        val result = m1.toString

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(3 -> geeks, 4 -> for)

```

**例 2:**

```scala
// Scala program of toString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying toString method
        val result = m1.toString

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(3 -> geeks, 4 -> for, 2 -> cs)

```