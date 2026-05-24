# Scala 可变排序 Map copyToArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-mutatable-sorted map-copy to array-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-copytoarray-method-with-example/)

**复制到数组()**方法用于将排序映射的键对复制到数组中。

> **方法定义:** def copyToArray(xs: Array[(A，B)]:Unit
> 
> **返回类型:**它将 SortedMap 的键返回到一个数组。

**示例#1:**

```scala
// Scala program of copyToArray()
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

        // Creating Array 
        val x: Array[Any] = Array(0, 0, 0, 0, 0) 

        // using 'copyToArray' method 
        m1.copyToArray(x) 

        // Displays keys copied in 
        // the Array 
        for(m2 <-x) 
        println(m2) 
    }
}
```

**输出:**

```scala
(cs, 2)
(for, 3)
(geeks, 5)
0
0

```