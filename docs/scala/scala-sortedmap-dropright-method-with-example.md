# Scala SortedMap dropRight()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-dropright-method-with-example/)

利用 **dropRight()** 方法删除最后的‘n’个元素。

> **方法定义:**def drop right(n:Int):SortedMap[A，B]
> 
> **返回类型:**它返回 sorted map 中除最后‘n’个元素之外的所有元素。

**示例#1:**

```scala
// Scala program of dropRight()
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

        // Applying dropRight method
        val result = m1.dropRight(1)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Map(cs -> 5, for -> 3)

```