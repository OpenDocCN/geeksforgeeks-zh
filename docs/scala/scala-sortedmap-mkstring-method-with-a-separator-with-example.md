# 带分隔符的 Scala SortedMap mkString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-MK string-method-with-separator-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-mkstring-method-with-a-separator-with-example/)

此方法与 **mkString()** 方法相同，但此处还添加了一个分隔符。

> **方法定义:**def mkString(sep:String):String
> 
> **返回类型:**它以字符串形式返回 SortedMap 的元素以及它们之间的分隔符。

**示例#1:**

```scala
// Scala program of mkString()
// method with a separator
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying mkString method 
        val result = m1.mkString("/")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
cs -> 2/for -> 3/geeks -> 5

```

**例 2:**

```scala
// Scala program of mkString()
// method with a separator
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "geeks" -> 5)

        // Applying mkString method 
        val result = m1.mkString("/")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
for -> 3/geeks -> 5

```