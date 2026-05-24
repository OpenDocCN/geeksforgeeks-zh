# Scala SortedMap filterKeys()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted map-filter keys-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-filterkeys-method-with-example/)

**filterKeys()** 方法用于查找所有键满足给定谓词的对。

> **方法定义:**def filterKeys(p:(A)=>Boolean:SortedMap[A，B]
> 
> **返回类型:**它返回 sorted map 的所有“键值”对，其中键满足给定的谓词。

**示例#1:**

```scala
// Scala program of filterKeys()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap(5 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying filterKeys method
        val result = m1.filterKeys(_ > 2)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Map(4 -> for, 5 -> geeks)

```