# Scala 可变排序映射到字符串()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted map-tostring-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-tostring-method-with-example/)

**toString()** 方法用于显示 Scala SortedMap 中的字符串。

> **方法定义:** def toString(): String
> 
> **返回类型:**从指定的 SortedMap 返回一个字符串。

**示例#1:**

```scala
// Scala program of toString()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 4 -> "for")

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
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying toString method
        val result = m1.toString

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(2 -> cs, 3 -> geeks, 4 -> for)

```