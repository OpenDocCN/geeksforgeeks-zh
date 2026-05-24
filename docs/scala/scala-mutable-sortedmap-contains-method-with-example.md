# Scala 可变排序映射包含()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted map-contains-method-with-example/](https://www.geeksforgeeks.org/scala-mutable-sortedmap-contains-method-with-example/)

Scala 的 **contains()** 方法相当于 Scala 的 *isDefinedAt* 方法，但唯一的区别是在所有 *PartialFunction* 类上都观察到了 *isDefinedAt* ，而 *contains* 则明确定义为 Scala 的 *SortedMap* 接口。它检查声明的 SortedMap 是否包含键绑定。

> **方法定义:** def 包含(键:K):布尔
> 其中， *k* 是关键。
> 
> **返回类型:**如果 SortedMap 声明的键有绑定，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of contains()
// method
import scala.collection.SortedMap

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying contains method
        val result = m1.contains(3)

        // Displays output
        println(result)

    }
}                                         

```

**Output:**

```scala
true

```