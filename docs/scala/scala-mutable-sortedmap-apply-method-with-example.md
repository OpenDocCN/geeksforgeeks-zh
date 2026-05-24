# Scala 可变排序应用()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted map-apply-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-apply-method-with-example/)

**apply()** 用于在所述排序地图中搜索关键字。

> **方法定义:**m1 . apply(“key”)
> 这里 m1 是 SortedMap。
> 
> **返回类型:**返回要搜索的关键字的值。

**示例#1:**

```scala
// Scala program of apply()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "geeks" -> 5)

        // Applying apply method
        val result = m1.apply("for") 

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
3

```