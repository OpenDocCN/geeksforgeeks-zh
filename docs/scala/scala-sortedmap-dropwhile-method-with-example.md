# Scala SortedMap dropWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted map-drop while-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-dropwhile-method-with-example/)

使用 **dropWhile()** 方法删除元素，直到满足所述条件。

> **方法定义:** def dropWhile(p: ((A，B))=>Boolean:sorted map[A，B]
> 
> **返回类型:**它返回所述 SortedMap 的元素的最长后缀，其第一个元素不满足谓词 p。

**示例#1:**

```scala
// Scala program of dropWhile()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying dropWhile method
        val result = m1.dropWhile(z=>false) 

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(cs -> 2, for -> 3, geeks -> 5)

```

**例 2:**

```scala
// Scala program of dropWhile()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying dropWhile method
        val result = m1.dropWhile(z=>true) 

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map()

```