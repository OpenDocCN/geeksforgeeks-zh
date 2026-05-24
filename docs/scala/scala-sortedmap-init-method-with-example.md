# Scala SortedMap init()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-init-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-init-method-with-example/)

**init()** 方法用于删除 SortedMap 的最后一个元素。它将返回 SortedMap 的所有元素，除了最后一个。

> **方法定义:**定义初始化:排序映射[A，B]
> 
> **返回类型:**返回 SortedMap 中除最后一个元素以外的所有元素。

**示例#1:**

```scala
// Scala program of init()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs"-> 2)

        // Applying init method
        val result = m1.init

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(cs -> 2, for -> 3)

```

**例 2:**

```scala
// Scala program of init()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5)

        // Applying init method
        val result = m1.init

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map()

```