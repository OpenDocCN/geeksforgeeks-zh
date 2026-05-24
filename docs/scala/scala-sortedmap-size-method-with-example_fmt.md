# Scala SortedMap size()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-sortedmap-size-method-with-example/](https://www.geeksforgeeks.org/scala-sortedmap-size-method-with-example/)

`size()`用于查找所述排序映射中键值对的数量。

> **方法定义:** `def size: Int`
>
> **返回类型:** 返回 `SortedMap` 中的元素个数。

**示例#1:**

```scala
// Scala program of size()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 1 -> "for", 2 -> "cs")

// Applying size method
        val result = m1.size

// Displays output
        println(result)

}
}
```

**Output:**

```scala
3
```

**例 2:**

```scala
// Scala program of size()
// method
import scala.collection.immutable.SortedMap

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a SortedMap
        val m1 = SortedMap(3 -> "geeks", 1 -> "for", 1 -> "cs")

// Applying size method
        val result = m1.size

// Displays output
        println(result)

}
}
```

**Output:**

```scala
2
```