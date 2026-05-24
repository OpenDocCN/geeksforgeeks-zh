# Scala 可变排序键()方法示例

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted map-keys-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-keys-method-with-example/)

**键()**方法用于给出 SortedMap 的所有键的迭代器。

> **方法定义:**定义键:可迭代的【A】
> 
> **返回类型:**它返回一个遍历 SortedMap 所有键的迭代器。

**示例#1:**

```scala
// Scala program of keys()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating SortedMap
        val m1 = SortedMap("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying keys method 
        val result = m1.keys

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
Set(cs, for, geeks)

```