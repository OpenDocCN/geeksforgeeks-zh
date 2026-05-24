# Scala SortedMap equals()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted map-equals-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-equals-method-with-example/)

**等于()**方法用于检查两个排序的映射是否具有相同的键值对。

> **方法定义:** def 等于(即:任意):布尔值
> 
> **返回类型:**如果两个排序映射的键值对相同，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of equals()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMaps
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs"-> 2)
        val m2 = SortedMap("cs" -> 2, "for" -> 3, "geeks"-> 5)

        // Applying equals method
        val result = m1.equals(m2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of equals()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMaps
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs"-> 2)
        val m2 = SortedMap("cs" -> 2, "fo" -> 2, "geeks"-> 5)

        // Applying equals method
        val result = m1.equals(m2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false

```