# Scala SortedMap mkString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-mkstring-method-with-example/)

**mkString()** 方法用于将 SortedMap 的元素表示为字符串。

> **方法定义:** def mkString: String
> 
> **返回类型:**它以字符串形式返回 SortedMap 的元素。

**示例#1:**

```scala
// Scala program of mkString()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 6)

        // Applying mkString method 
        val result = m1.mkString

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
cs -> 6for -> 3geeks -> 5

```

**例 2:**

```scala
// Scala program of mkString()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "for" -> 3)

        // Applying mkString method 
        val result = m1.mkString

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
for -> 3geeks -> 5

```