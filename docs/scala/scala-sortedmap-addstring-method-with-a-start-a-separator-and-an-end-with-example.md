# Scala SortedMap addString()方法，以示例

开头、分隔符和结尾

> 原文:[https://www . geesforgeks . org/Scala-sorted map-add string-method-with-start-a-separator-and-end-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-addstring-method-with-a-start-a-separator-and-an-end-with-example/)

该方法与 **addString()** 方法相同，但这里还包括一个开始、一个分隔符和一个结束。

> **方法定义:** def addString(sb:可变。StringBuilder，开始:String，sep: String，结束:String):可变。StringBuilder
> 
> 其中， *sep* 是所述的分隔符。
> 
> **返回类型:**返回字符串生成器中 SortedMap 的元素，这里还包括一个开始、一个分隔符和一个结束。

**示例#1:**

```scala
// Scala program of addString() method
// with a start, a separator and an
// end
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 3)

        // Applying addString method 
        val result = m1.addString(new StringBuilder(), ">>>", "|", "--")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
>>>cs -> 3|for -> 3|geeks -> 5--

```

**例 2:**

```scala
// Scala program of addString() method
// with a start, a separator and an
// end
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "for" -> 3)

        // Applying addString method 
        val result = m1.addString(new StringBuilder(), ">>>", "|", "--")

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
>>>for -> 3|geeks -> 5--

```

所以，这里删除了相同的键。