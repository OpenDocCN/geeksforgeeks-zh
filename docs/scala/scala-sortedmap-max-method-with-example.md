# Scala SortedMap max()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-max-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-max-method-with-example/)

利用 **max()** 方法寻找 SortedMap 的最大元素。

> **方法定义:** def 最大值:(A，B)
> 
> **返回类型:**返回 SortedMap 的最大元素。

**示例#1:**

```scala
// Scala program of max()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying max method 
        val result = m1.max

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
(geeks, 5)

```

**例 2:**

```scala
// Scala program of max()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "geeks" -> 6)

        // Applying max method 
        val result = m1.max

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
(geeks, 6)

```