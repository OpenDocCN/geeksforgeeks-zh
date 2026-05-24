# Scala SortedMap addString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted map-add string-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-addstring-method-with-example/)

**添加字符串()**方法用于将 SortedMap 的元素添加到字符串生成器中。

> **方法定义:**def addString(b:StringBuilder):StringBuilder
> 
> **返回类型:**返回字符串生成器中的元素。

**示例#1:**

```scala
// Scala program of addString()
// method
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
        val result = m1.addString(new StringBuilder()) 

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
cs -> 2for -> 3geeks -> 5

```