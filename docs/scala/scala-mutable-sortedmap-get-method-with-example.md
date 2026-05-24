# Scala 可变排序 Map get()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted map-get-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-get-method-with-example/)

**get()** 方法用于给出与 SortedMap 的键相关联的值。这些值在这里作为一个选项返回，即以“部分”或“无”的形式返回。

> **方法定义:** def get(键:A):Option【B】
> 
> **返回类型:**返回方法中给定值对应的键作为参数。

**示例#1:**

```scala
// Scala program of get()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2) 

        // Applying get method
        val result = m1.get("for")

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Some(3)

```