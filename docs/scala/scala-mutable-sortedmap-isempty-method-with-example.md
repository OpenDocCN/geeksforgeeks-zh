# Scala 可变排序 Map isEmpty()方法示例

> 原文:[https://www . geesforgeks . org/Scala-mutable-sorted map-isempty-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-isempty-method-with-example/)

**isEmpty()** 方法用于检查给定的 SortedMap 是否为空。

> **方法定义:**定义为空:布尔值
> 
> **返回类型:**如果所述的 SortedMap 为空，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of isEmpty()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap(3 -> "geeks", 1 -> "for", 2 -> "cs", 3 -> "geeks")

        // Applying isEmpty method 
        val result = m1.isEmpty

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
// Scala program of isEmpty()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap(2 -> 4)

        // Applying isEmpty method 
        val result = m1.isEmpty

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
false

```