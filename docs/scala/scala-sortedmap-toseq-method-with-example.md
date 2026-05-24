# Scala SortedMap toSeq()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-toseq-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-toseq-method-with-example/)

**toSeq()** 方法用于显示 Scala SortedMap 中的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**它从指定的 SortedMap 返回一个序列。

**示例#1:**

```scala
// Scala program of toSeq()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying toSeq method
        val result = m1.toSeq

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
ArrayBuffer((3, geeks), (4, for))

```

**例 2:**

```scala
// Scala program of toSeq()
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

        // Applying toSeq method
        val result = m1.toSeq

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
ArrayBuffer((2, cs), (3, geeks), (4, for))

```