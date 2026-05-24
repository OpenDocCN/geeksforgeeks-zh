# Scala SortedMap count()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted map-count-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-count-method-with-example/)

利用**计数()**方法对 SortedMap 中的键对进行计数。

> **方法定义:** def count(p: ((A，B))=>Boolean:Int
> 
> **返回类型:**它返回 SortedMap 中满足给定谓词的键的数量。

**示例#1:**

```scala
// Scala program of count()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 5)

        // Applying count method
        val result = m1.count(z=>true)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
3

```