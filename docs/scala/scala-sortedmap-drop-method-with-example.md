# Scala SortedMap drop()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-drop-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-drop-method-with-example/)

使用 **drop()** 方法删除前 n 个元素。

> **方法定义:** def drop(n: Int): SortedMap[A，B]
> 
> **返回类型:**它返回 SortedMap 中除了前‘n’个元素之外的所有元素。

**示例#1:**

```scala
// Scala program of drop()
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

        // Applying drop method
        val result = m1.drop(1)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Map(for -> 3, geeks -> 5)

```