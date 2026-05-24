# Scala SortedMap exists()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted map-exists-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-exists-method-with-example/)

**exists()** 方法用于检查给定的谓词是否满足 SortedMap 的元素。

> **方法定义:** def 存在(p:(A，B)) = >布尔型:布尔型
> 
> **返回类型:**如果所述谓词对 SortedMap 的某些元素成立，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of exists()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3)

        // Applying exists method
        val result = m1.exists(x => x._1 == "for" && x._2 == 3)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
true

```

因此，这里陈述的谓词对于第二个**键值**对是真的，所以返回真。
**例 2:**

```scala
// Scala program of exists()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3)

        // Applying exists method
        val result = m1.exists(x => x._1 == "geeks" && x._2 == 3)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false

```