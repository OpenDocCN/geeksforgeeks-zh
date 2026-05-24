# 带分隔符的 Scala SortedMap addString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-add string-method-with-separator-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-addstring-method-with-a-separator-with-example/)

该方法与 **addString()** 方法相同，但这里还包括一个分隔符。

> **方法定义:**def addString(b:StringBuilder，sep:String):StringBuilder
> 
> 其中， *sep* 为所述分隔符。
> 
> **返回类型:**它在字符串生成器中返回 SortedMap 的元素，并且在 SortedMap 的元素之间还添加了一个分隔符。

**示例#1:**

```scala
// Scala program of addString()
// method with a separator
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying addString method
        // and a separator
        val result = m1.addString(new StringBuilder(), "_") 

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
cs -> 2_for -> 3_geeks -> 5

```

**例 2:**

```scala
// Scala program of addString()
// method with a separator
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "geeks" -> 2)

        // Applying addString method
        // and a separator
        val result = m1.addString(new StringBuilder(), "_") 

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
for -> 3_geeks -> 2

```

所以，这里删除了相同的键。