# Scala SortedMap tail()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted map-tail-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-tail-method-with-example/)

**tail()** 方法用于显示除第一个元素之外的 SortedMap 的所有元素。

> **方法定义:**定义尾部:排序地图【A，B】
> 
> **返回类型:**返回除第一个元素之外的所述 SortedMap 的所有元素。

**示例#1:**

```scala
// Scala program of tail()
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

        // Applying tail method
        val result = m1.tail

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
// Scala program of tail()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 3 -> "geeks")

        // Applying tail method
        val result = m1.tail

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(4 -> for)

```