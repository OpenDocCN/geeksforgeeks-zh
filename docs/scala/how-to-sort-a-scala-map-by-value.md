# 如何按值对 Scala 地图进行排序

> 原文:[https://www . geeksforgeeks . org/如何按值排序 Scala-map/](https://www.geeksforgeeks.org/how-to-sort-a-scala-map-by-value/)

在本文中，我们将学习如何按值对 Scala 映射进行排序。我们可以使用 **sortBy** 方法，按键从低到高或从高到低对地图进行排序。

**语法:**

```scala
MapName.toSeq.sortBy(_._2):_*
```

让我们试着用更好的例子来理解它。

**示例#1:**

## 斯卡拉

```scala
// Scala program to sort given map by value
import scala.collection.immutable.ListMap

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val mapIm = Map("Zash" -> 30,
                        "Jhavesh" -> 20,
                        "Charlie" -> 50)

        // Sort the map by value
        val res = ListMap(mapIm.toSeq.sortBy(_._2):_*)
        println(res)
    }
}
```

**输出:**

```scala
Map(Jhavesh -> 20, Zash -> 30, Charlie -> 50)
```