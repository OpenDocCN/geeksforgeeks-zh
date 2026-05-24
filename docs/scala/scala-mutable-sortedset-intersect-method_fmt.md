# Scala 可变排序集 intersect() 方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedset-intersect-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-intersect-method/)

在 Scala 可变集合中，`SortedSet` 的 `intersect()` 方法用于计算两个 sorted set 之间的交集。

## 方法定义

`def intersect(that: SortedSet[A]): SortedSet[A]`

**返回类型:** 它返回一个包含两个排序集中元素的排序集。

## 示例

**示例 #1:**

```scala
// Scala program of intersect()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(1, 12, 3, 14, 5)
        val s2 = SortedSet(11, 2, 3, 14, 5)

        // Applying intersect method
        val s3 = s1.intersect(s2)

        s3.foreach(x => println(x))
    }
}
```

**Output:**

```scala

```

**示例 #2:**

```scala
// Scala program of intersect()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(11, 22, 33, 44, 55)
        val s2 = SortedSet(11, 2, 3, 4, 5)

        // Applying intersect method
        val s3 = s1.intersect(s2)

        s3.foreach(x => println(x))
    }
}
```

**Output:**

```scala

```