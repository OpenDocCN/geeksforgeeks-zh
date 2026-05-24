# Scala SortedMap filter()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted map-filter-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-filter-method-with-example/)

**过滤器()**方法用于选择满足所述谓词的 SortedMap 的所有元素。

> **方法定义:** def filter(p: ((A，B))=>Boolean:SortedMap[A，B]
> 
> **返回类型:**它返回一个新的 SortedMap，由满足给定谓词的 sorted map 的所有元素组成。

**示例#1:**

```scala
// Scala program of filter()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3)

        // Applying filter method
        val result = m1.filter(x => x._1 == "geeks" && x._2 == 5)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Map(geeks -> 5)

```