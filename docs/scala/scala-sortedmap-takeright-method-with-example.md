# Scala sorted map taker right()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted map-taker ight-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-takeright-method-with-example/)

**taker right()**方法用于选择排序地图的最后 n 个元素。

> **方法定义:**def taker right(n:Int):sorted map[A，B]
> 
> **返回类型:**返回 SortedMap 的最后‘n’个元素。

**示例#1:**

```scala
// Scala program of takeRight()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying takeRight method
        val result = m1.takeRight(2)

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
// Scala program of takeRight()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying takeRight method
        val result = m1.takeRight(4)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(2 -> cs, 3 -> geeks, 4 -> for)

```