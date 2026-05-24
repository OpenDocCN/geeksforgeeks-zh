# 如何通过键

对 Scala 地图进行排序

> 原文:[https://www . geeksforgeeks . org/如何按键排序 Scala-map/](https://www.geeksforgeeks.org/how-to-sort-a-scala-map-by-key/)

Map 与保存键:值对的字典相同。在本文中，我们将学习如何按键对 Scala 映射进行排序。我们可以使用**排序按**键从低到高或从高到低对地图进行排序。
**语法:**

```scala
mapName.toSeq.sortBy(_._1):_*
```

让我们试着用更好的例子来理解它。
**例 1:**

```scala
// Scala program to sort given map by key
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

        // Sort map by key
        val res = ListMap(mapIm.toSeq.sortBy(_._1):_*)
        println(res)
    } 
} 
```

**Output:**

```scala
Map(Charlie -> 50, Jhavesh -> 20, Zash -> 30)

```

**例 2:**

```scala
// Scala program to sort given map by key
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

        // reverse map in ascending order
        val res = ListMap(mapIm.toSeq.sortWith(_._1 < _._1):_*)
        println(res)
    } 
} 
```

**Output:**

```scala
Map(Charlie -> 50, Jhavesh -> 20, Zash -> 30)

```

**示例#3:**

```scala
// Scala program to sort given map by key
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

        // reverse map in descending order
        val res = ListMap(mapIm.toSeq.sortWith(_._1 > _._1):_*)
        println(res)
    } 
} 
```

**Output:**

```scala
Map(Zash -> 30, Jhavesh -> 20, Charlie -> 50)

```