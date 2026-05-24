# Scala 可变 SortedMap mkString()方法，有一个开始、一个分隔符和一个结束，示例为

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted map-mkstring-method-with-start-a-separator-end-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-mkstring-method-with-a-start-a-separator-and-an-end-with-example/)

此方法与 **mkString()** 相同，但这里还增加了一个开始、一个分隔符和一个结束。

> **方法定义:** defmkString(开始:String，sep: String，结束:String): String
> 
> **返回类型:**它将 SortedMap 的元素作为一个字符串返回，并带有指定的开始、分隔符和结束。

**示例#1:**

```scala
// Scala program of mkString() method
// with a start, a separator and an
// end
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying mkString method 
        val result = m1.mkString(">>>", "|", "--")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
>>>cs -> 2|for -> 3|geeks -> 5--

```

**例 2:**

```scala
// Scala program of mkString() method
// with a start, a separator and an
// end
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "for" -> 3)

        // Applying mkString method 
        val result = m1.mkString(">>>", "|", "--")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
>>>for -> 3|geeks -> 5--

```